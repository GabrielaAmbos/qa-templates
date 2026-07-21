# 🔗 Matriz de Rastreabilidade de Requisitos (RTM)

> **Como usar:** mantenha esta matriz atualizada durante o ciclo de testes para enxergar cobertura e lacunas — cada requisito deve ter ao menos um caso de teste. Em ferramentas como Jira + Xray ou Azure DevOps a rastreabilidade pode ser gerada automaticamente; use este template quando o processo for manual.

---

## Matriz de Rastreabilidade — [Projeto / Release X]

| Campo | Informação |
| --- | --- |
| **Projeto** | [Nome] |
| **Release / sprint** | [1.4.0 / Sprint 12] |
| **Responsável** | [Nome do QA] |
| **Última atualização** | [DD/MM/AAAA] |

---

## Matriz

| Requisito | Descrição resumida | Prioridade | Casos de teste | Status dos testes | Defeitos | Cobertura |
| --- | --- | :---: | --- | :---: | --- | :---: |
| [REQ-001] | [Login com e-mail e senha] | Alta | [CT-001, CT-002, CT-003] | ✅ | — | ✅ Coberto |
| [REQ-002] | [Recuperação de senha] | Alta | [CT-004, CT-005] | ❌ | [BUG-123] | ✅ Coberto |
| [REQ-003] | [Login social (Google)] | Média | [CT-006] | 🚫 | — | ⚠️ Parcial |
| [REQ-004] | [Bloqueio após N tentativas] | Alta | — | — | — | ❌ Sem cobertura |

**Legenda de status:** ✅ Todos passaram · ❌ Ao menos um falhou · 🚫 Bloqueado · ⬜ Não executado

---

## Resumo de cobertura

| Métrica | Valor |
| --- | --- |
| Total de requisitos | [4] |
| Cobertos por casos de teste | [3] ([75%]) |
| Sem cobertura | [1] — [REQ-004] |
| Requisitos com defeito em aberto | [1] — [REQ-002] |

## Ações para lacunas identificadas

| Lacuna | Ação | Responsável | Prazo |
| --- | --- | --- | --- |
| [REQ-004 sem caso de teste] | [Escrever CT-007 e CT-008] | [Nome do QA] | [DD/MM] |
