# 🔄 Caso de Teste de API / Integração (execução manual)

> **Como usar:** para testes manuais de integração que vão além da resposta da API — validando o efeito da ação nas outras camadas: banco de dados, mensageria (Kafka, RabbitMQ, SQS), cache, logs e sistemas integrados. Copie um bloco por cenário. Liste no início **onde** verificar cada camada, para que qualquer pessoa do time consiga executar.

---

## [CTI-000] — [Título do cenário de integração]

| Campo | Informação |
| --- | --- |
| **ID** | [CTI-000] |
| **Fluxo de negócio** | [Criação de pedido com pagamento aprovado] |
| **História/Requisito** | [link] |
| **Sistemas envolvidos** | [API de pedidos → banco `orders` → fila `pedido-criado` → serviço de estoque] |
| **Prioridade** | [Alta / Média / Baixa] |
| **Autor** | [Nome do QA] |

## Acessos necessários

*Onde e como verificar cada camada — sem isso o teste não é reprodutível por outra pessoa.*

| Camada | Ferramenta / acesso | Onde obter credencial |
| --- | --- | --- |
| API | [Postman — coleção X / Swagger homolog] | [cofre de senhas — nunca commitar] |
| Banco de dados | [DBeaver → host homolog, schema `orders`] | [acesso solicitado ao time Y] |
| Mensageria | [Kafka UI / RabbitMQ Management / console AWS SQS — URL] | [...] |
| Logs / observabilidade | [Kibana / Grafana / Datadog — dashboard Z] | [...] |

## Pré-condições

- [Usuário de teste com perfil cliente ativo — id `abc-123`]
- [Produto `xyz-789` com estoque ≥ 2 no ambiente]
- [Consumidor do serviço de estoque rodando em homolog — verificar em (link)]

---

## Passos e validações por camada

### Passo 1 — Executar a ação via API

**Request:** `[POST /api/v1/pedidos]`

```json
{
  "itens": [{ "produtoId": "xyz-789", "quantidade": 2 }],
  "formaPagamento": "PIX"
}
```

**Validar na resposta:**

- [ ] Status `[201 Created]` em até [X s]
- [ ] Corpo com `[pedidoId]` gerado e `status: "AGUARDANDO_PAGAMENTO"`
- [ ] [Header `correlation-id` presente — anotar para rastrear nos logs]

### Passo 2 — Validar a persistência no banco

*Consulta de apoio (ajuste ao seu schema):*

```sql
SELECT id, status, valor_total, criado_em
FROM pedidos
WHERE id = '[pedidoId retornado]';
```

**Validar:**

- [ ] Registro criado com os valores enviados (itens, quantidades, valor calculado)
- [ ] `[status]` = `[AGUARDANDO_PAGAMENTO]`; `[criado_em]` preenchido com data/hora atual (timezone correto)
- [ ] Tabelas relacionadas consistentes ([`pedido_itens` com 1 linha por item])
- [ ] Nenhum dado sensível gravado em texto claro que devesse estar mascarado/criptografado

### Passo 3 — Validar a publicação na mensageria

**Onde:** [tópico `pedido-criado` no Kafka UI / fila no RabbitMQ]

**Validar:**

- [ ] Mensagem publicada em até [X s] após a criação
- [ ] Payload conforme contrato — campos, tipos e `[pedidoId]` correto:

```json
{
  "evento": "PEDIDO_CRIADO",
  "pedidoId": "...",
  "valorTotal": 180.00,
  "timestamp": "ISO 8601"
}
```

- [ ] [Chave de particionamento / headers conforme especificação]
- [ ] Mensagem **não** duplicada (uma ação → uma mensagem)

### Passo 4 — Validar o efeito no sistema consumidor

**Onde:** [serviço de estoque — endpoint de consulta / tabela `reservas`]

**Validar:**

- [ ] [Estoque do produto `xyz-789` reservado em 2 unidades]
- [ ] [Consulta `GET /api/v1/estoque/xyz-789` reflete a reserva]
- [ ] Tempo entre a publicação e o processamento dentro do esperado ([< X s])

### Passo 5 — Validar logs e observabilidade

- [ ] Logs da transação localizáveis pelo `[correlation-id]` em todas as pontas
- [ ] Nenhum erro/exception não esperado no período do teste
- [ ] [Métricas/traces registrados no dashboard, se aplicável]

---

## Cenários de exceção da integração

*A parte que mais encontra bug em integração — o que acontece quando uma ponta falha:*

| # | Cenário | Como simular | Resultado esperado |
| :---: | --- | --- | --- |
| 1 | Consumidor fora do ar durante a publicação | [Parar o serviço de estoque / pausar o consumidor] | [Mensagem permanece na fila; processada quando o serviço volta; sem perda] |
| 2 | Mensagem com payload inválido | [Publicar manualmente mensagem malformada no tópico] | [Vai para DLQ (dead letter queue); alerta gerado; consumidor não trava] |
| 3 | Reprocessamento da mesma mensagem | [Republicar a mesma mensagem] | [Idempotência: efeito não duplica (estoque não reserva 2×)] |
| 4 | Timeout do banco durante a gravação | [Se possível simular] | [API retorna erro adequado; sem registro parcial/órfão; sem mensagem publicada] |
| 5 | Falha após gravar e antes de publicar | [Conforme arquitetura — outbox?] | [Garantia de consistência conforme desenho: mensagem publicada posteriormente ou transação revertida] |

---

## Execução

| Campo | Informação |
| --- | --- |
| **Executado por** | [Nome] |
| **Data / ambiente / versão** | [DD/MM/AAAA — homolog — release/1.4.0] |
| **Status** | ⬜ Não executado · ✅ Passou · ❌ Falhou · 🚫 Bloqueado |
| **Evidências** | [prints da resposta, do banco, da fila e dos logs — organizados por passo] |
| **Defeitos** | [links] |
