# 🔍 Post-mortem de Defeito em Produção

> **Como usar:** para defeitos relevantes que escaparam para produção (críticos, altos, ou recorrentes). O objetivo é aprender e prevenir, **nunca apontar culpados** — post-mortem blameless. Realize em até [1 semana] após a resolução, com Dev, QA e PO.

---

## Post-mortem — [Título curto do incidente]

| Campo | Informação |
| --- | --- |
| **Defeito** | [link do BUG-XXX] |
| **Severidade** | [🔴 Crítica / 🟠 Alta] |
| **Detectado em** | [DD/MM/AAAA HH:MM] — por [monitoramento / cliente / suporte / time] |
| **Resolvido em** | [DD/MM/AAAA HH:MM] — duração do impacto: [Xh] |
| **Facilitador** | [Nome] |
| **Participantes** | [nomes] |

---

## 1. O que aconteceu

*Descrição objetiva do problema e do impacto, sem julgamento.*

Ex.: Entre DD/MM HH:MM e DD/MM HH:MM, usuários que aplicavam cupom no checkout recebiam erro 500. Estimados [X] pedidos perdidos ([R$ Y]). Detectado por reclamações no suporte, não pelo monitoramento.

**Impacto:**

- Usuários afetados: [quantos / que perfil]
- Impacto de negócio: [receita, SLA, reputação]
- Tempo até detecção: [Xh] · Tempo até correção: [Yh]

## 2. Linha do tempo

| Data/hora | Evento |
| --- | --- |
| [DD/MM HH:MM] | [Deploy da release 1.4.0 com a alteração X] |
| [DD/MM HH:MM] | [Primeiras reclamações no suporte] |
| [DD/MM HH:MM] | [Time acionado; investigação iniciada] |
| [DD/MM HH:MM] | [Causa identificada] |
| [DD/MM HH:MM] | [Hotfix 1.4.1 em produção; normalização confirmada] |

## 3. Causa raiz (5 porquês)

1. **Por que o erro ocorreu?** [O serviço de cupons lançava exceção para cupons do tipo Y]
2. **Por quê?** [O novo cálculo de desconto não tratava o tipo Y]
3. **Por quê?** [O tipo Y não estava descrito na história nem nos critérios de aceite]
4. **Por quê?** [O mapeamento de tipos de cupom existentes não foi levantado no refinamento]
5. **Por quê?** [Não há passo de análise de impacto sobre dados de produção no refinamento]

**Causa raiz:** [processo/técnica — não uma pessoa]

## 4. Por que os testes não pegaram?

*A pergunta central para o QA — respondida sem defensividade.*

- [ ] O cenário estava previsto nos casos de teste? [Não — tipo Y não era conhecido]
- [ ] Havia massa de dados representativa? [Homolog não tinha cupons do tipo Y]
- [ ] A automação cobria o fluxo? [Cobria apenas o caminho feliz]
- [ ] Era detectável por monitoramento? [Sim, mas não havia alerta de taxa de erro no checkout]

## 5. Ações preventivas

*Cada ação com dono e prazo — sem dono, não é ação, é desejo.*

| # | Ação | Tipo | Responsável | Prazo | Status |
| :---: | --- | --- | --- | --- | :---: |
| 1 | [Criar massa de dados espelhando os tipos de cupom de produção] | Teste | [QA] | [DD/MM] | ⬜ |
| 2 | [Adicionar cenários de tipo Y à suíte de regressão] | Teste | [QA] | [DD/MM] | ⬜ |
| 3 | [Alerta de taxa de erro > X% no checkout] | Monitoramento | [Dev] | [DD/MM] | ⬜ |
| 4 | [Incluir análise de dados de produção no DoR] | Processo | [Time] | [DD/MM] | ⬜ |

## 6. O que funcionou bem

*Reconheça o que acelerou a detecção/resolução — para repetir.*

- [Rollback executado em X minutos conforme plano]
