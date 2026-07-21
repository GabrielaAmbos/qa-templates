# 🔌 Template — Teste de API

> **Como usar:** um bloco por endpoint. Serve tanto para documentar testes manuais (Postman/Insomnia/Bruno) quanto como especificação para automação. Combine com a coleção exportada da ferramenta versionada no repositório.

---

## Endpoint: [POST /api/v1/pedidos]

| Campo | Informação |
| --- | --- |
| **Descrição** | [Cria um novo pedido para o usuário autenticado] |
| **Documentação** | [link do Swagger/OpenAPI] |
| **Autenticação** | [Bearer token — perfil necessário: cliente] |
| **Ambiente** | [https://api-homolog.sistema.com] |
| **Responsável** | [Nome do QA] |

### Request de exemplo

```json
{
  "itens": [
    { "produtoId": "abc-123", "quantidade": 2 }
  ],
  "cupom": "PROMO10"
}
```

### Response de sucesso esperada — `201 Created`

```json
{
  "pedidoId": "uuid",
  "status": "AGUARDANDO_PAGAMENTO",
  "valorTotal": 180.00
}
```

---

## Cenários de teste

### Casos de sucesso

| # | Cenário | Entrada | Esperado |
| :---: | --- | --- | --- |
| 1 | [Criação com payload válido] | [payload de exemplo] | [201 + corpo com pedidoId; pedido consultável via GET] |
| 2 | [Criação com cupom válido] | [cupom PROMO10] | [201 + valorTotal com desconto aplicado] |

### Validação de contrato

- [ ] Campos, tipos e formatos da resposta conforme documentação (nada a mais, nada a menos)
- [ ] Campos monetários com precisão correta; datas em [ISO 8601]
- [ ] Headers esperados presentes ([Content-Type, correlation-id])

### Casos de erro

| # | Cenário | Entrada | Esperado |
| :---: | --- | --- | --- |
| 1 | Sem token de autenticação | [header Authorization ausente] | `401` + mensagem padrão |
| 2 | Token de outro perfil sem permissão | [token de perfil X] | `403` |
| 3 | Payload vazio / malformado | `{}` / JSON inválido | `400` + lista de campos com erro |
| 4 | Campo obrigatório ausente | [sem `itens`] | `400` indicando o campo |
| 5 | Tipo errado | [`quantidade: "dois"`] | `400`, nunca `500` |
| 6 | Recurso inexistente | [`produtoId` inválido] | `404` ou `422` conforme padrão da API |
| 7 | Regra de negócio violada | [cupom expirado] | `422` + código de erro de negócio |
| 8 | Método não suportado | [PUT no endpoint] | `405` |

### Casos de borda e não funcionais

- [ ] **Idempotência/duplicação:** duas requisições idênticas em sequência não criam registro duplicado (quando aplicável)
- [ ] **Valores extremos:** quantidade 0, negativa, muito grande; strings no limite de tamanho; caracteres especiais e acentos persistidos corretamente
- [ ] **Paginação** (endpoints de listagem): página inexistente, `pageSize` extremo, ordenação
- [ ] **Tempo de resposta:** dentro do SLA esperado ([< X ms] em condições normais)
- [ ] **Mensagens de erro** não expõem stack trace ou detalhes internos

---

## Execução

| Campo | Informação |
| --- | --- |
| **Coleção da ferramenta** | [link/caminho da coleção Postman/Bruno versionada] |
| **Data / versão testada** | [DD/MM/AAAA — release/1.4.0] |
| **Resultado** | [X de Y cenários OK — bugs: links] |
