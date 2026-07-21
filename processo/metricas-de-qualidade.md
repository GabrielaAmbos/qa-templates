# 📈 Métricas de Qualidade — Relatório Periódico

> **Como usar:** relatório mensal (ou por sprint) para acompanhar tendências — o valor está na comparação entre períodos, não no número absoluto de um mês. Escolha poucas métricas e mantenha consistência. **Cuidado:** métricas viram meta e meta distorce comportamento (Lei de Goodhart) — use para conversa, não para cobrança individual.

---

## Métricas de Qualidade — [Mês/AAAA]

| Campo | Informação |
| --- | --- |
| **Projeto / time** | [Nome] |
| **Período** | [MM/AAAA] |
| **Responsável** | [Nome] |

---

## 1. Resumo do período

*3 linhas: destaque principal, tendência geral e ponto de atenção.*

## 2. Defeitos

| Métrica | Período anterior | Período atual | Tendência |
| --- | :---: | :---: | :---: |
| Defeitos encontrados em teste | [n] | [n] | [↑ ↓ →] |
| Defeitos encontrados em produção | [n] | [n] | [↑ ↓ →] |
| **Taxa de escape**¹ | [%] | [%] | [↑ ↓ →] |
| Defeitos críticos/altos em produção | [n] | [n] | [↑ ↓ →] |
| Tempo médio de correção (crítico/alto) | [Xd] | [Xd] | [↑ ↓ →] |
| Defeitos reabertos (correção que voltou) | [n] | [n] | [↑ ↓ →] |

¹ *Taxa de escape = produção ÷ (teste + produção). A métrica mais honesta sobre a eficácia dos testes.*

**Defeitos de produção por módulo:** [módulo X: n · módulo Y: n] — *concentração indica onde reforçar testes.*

## 3. Execução de testes

| Métrica | Período anterior | Período atual | Tendência |
| --- | :---: | :---: | :---: |
| Casos executados | [n] | [n] | [↑ ↓ →] |
| Taxa de aprovação na 1ª execução | [%] | [%] | [↑ ↓ →] |
| Histórias entregues sem retrabalho de teste | [%] | [%] | [↑ ↓ →] |

## 4. Automação

| Métrica | Período anterior | Período atual | Tendência |
| --- | :---: | :---: | :---: |
| Cobertura dos fluxos críticos | [%] | [%] | [↑ ↓ →] |
| Tempo de execução da suíte no CI | [min] | [min] | [↑ ↓ →] |
| Taxa de testes flaky | [%] | [%] | [↑ ↓ →] |
| Bugs pegos pela automação | [n] | [n] | [↑ ↓ →] |

## 5. Análise e ações

*O "por quê" por trás dos números — a parte mais importante do relatório.*

- **O que os números dizem:** [ex.: escape subiu puxado pelo módulo de pagamentos, que não tem regressão automatizada]
- **Ações para o próximo período:**

| Ação | Responsável | Prazo |
| --- | --- | --- |
| [Automatizar regressão de pagamentos — 5 fluxos principais] | [Nome] | [DD/MM] |

---

> **Anti-padrões a evitar:** medir QA por "quantidade de bugs abertos" (incentiva bug inflacionado), comparar times diferentes pela mesma régua, celebrar 100% de aprovação (pode significar teste fraco, não qualidade alta).
