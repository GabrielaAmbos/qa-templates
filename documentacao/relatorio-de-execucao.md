# 📊 Relatório de Execução de Testes

> **Como usar:** preencha ao final de cada ciclo de testes (sprint, release ou funcionalidade). O público é o time e os stakeholders — priorize clareza sobre exaustividade.

---

## Relatório de Execução — [Funcionalidade / Sprint / Release X]

| Campo | Informação |
| --- | --- |
| **Projeto** | [Nome] |
| **Ciclo de teste** | [Sprint 12 / Release 1.4.0] |
| **Período de execução** | [DD/MM] a [DD/MM/AAAA] |
| **Responsável** | [Nome do QA] |
| **Plano de teste** | [link] |

---

## 1. Resumo executivo

*3–5 linhas para quem só vai ler este parágrafo: o que foi testado, o resultado geral e o parecer.*

Ex.: Foram executados 42 dos 45 casos planejados para a funcionalidade de checkout. Foram encontrados 8 defeitos (1 alto, 4 médios, 3 baixos). O defeito alto foi corrigido e retestado. **Parecer: aprovado para produção.**

## 2. Métricas de execução

| Métrica | Valor |
| --- | --- |
| Casos planejados | [45] |
| Casos executados | [42] ([93%]) |
| ✅ Aprovados | [37] ([88%]) |
| ❌ Reprovados | [5] |
| 🚫 Bloqueados | [3] — [motivo] |
| Cobertura dos requisitos | [X de Y requisitos cobertos] |

## 3. Defeitos do ciclo

| Severidade | Abertos | Corrigidos e retestados | Adiados (com aval do PO) |
| --- | :---: | :---: | :---: |
| 🔴 Crítica | [0] | [0] | [0] |
| 🟠 Alta | [0] | [1] | [0] |
| 🟡 Média | [2] | [2] | [1] |
| 🟢 Baixa | [3] | [0] | [2] |

**Defeitos relevantes em aberto:**

| ID | Título | Severidade | Situação / acordo |
| --- | --- | --- | --- |
| [BUG-123] | [resumo] | 🟡 | [Corrigir na sprint 13 — acordado com PO em DD/MM] |

## 4. O que não foi testado e por quê

- [3 casos bloqueados pela indisponibilidade do gateway de pagamento em homolog]
- [Teste de carga adiado — sem ambiente dedicado]

## 5. Riscos residuais

*O que pode dar errado em produção considerando o que ficou de fora ou em aberto.*

- [Risco X — mitigação/monitoramento sugerido]

## 6. Parecer final

**[✅ Aprovado para produção / ⚠️ Aprovado com ressalvas / ❌ Reprovado]**

**Justificativa:** [...]

| Papel | Nome | Data | De acordo? |
| --- | --- | --- | :---: |
| QA | [Nome] | [DD/MM/AAAA] | ⬜ |
| Product Owner | [Nome] | [DD/MM/AAAA] | ⬜ |
