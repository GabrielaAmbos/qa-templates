# 🚦 Checklist Go/No-Go de Release

> **Como usar:** preencha na reunião de decisão de release, com Dev, QA, PO e (quando houver) Ops presentes. Qualquer item ❌ em seção crítica exige decisão explícita e registrada — quem aceitou o risco e por quê.

---

## Release [1.4.0] — Decisão de Go/No-Go

| Campo | Informação |
| --- | --- |
| **Data da reunião** | [DD/MM/AAAA] |
| **Versão / branch** | [release/1.4.0 — commit abc1234] |
| **Data planejada do deploy** | [DD/MM/AAAA HH:MM] |
| **Participantes** | [nomes e papéis] |

---

## 1. Qualidade (crítico)

- [ ] Suíte de regressão executada na versão candidata — [link do relatório]
- [ ] 100% dos casos críticos executados e aprovados
- [ ] Nenhum defeito crítico ou alto em aberto
- [ ] Defeitos médios/baixos em aberto listados e aceitos pelo PO (tabela abaixo)
- [ ] [Relatório de execução](../documentacao/relatorio-de-execucao.md) publicado com parecer do QA

**Defeitos conhecidos que sobem com a release:**

| ID | Título | Severidade | Aceito por | Plano |
| --- | --- | :---: | --- | --- |
| [BUG-123] | [resumo] | 🟡 | [PO — DD/MM] | [corrigir na 1.4.1] |

## 2. Técnica (crítico)

- [ ] Build da versão candidata gerado a partir da branch/tag correta
- [ ] Migrações de banco testadas em ambiente equivalente a produção
- [ ] Configurações/variáveis de ambiente de produção revisadas
- [ ] Dependências e integrações externas verificadas (versões, credenciais, quotas)
- [ ] **Plano de rollback definido e testado** — responsável: [nome]; tempo estimado: [X min]

## 3. Operação

- [ ] Janela de deploy definida e comunicada (horário de menor impacto)
- [ ] Monitoramento/alertas configurados para as novas funcionalidades
- [ ] Time de plantão/suporte ciente da release e dos defeitos conhecidos
- [ ] Feature flags configuradas (quando aplicável) — rollout: [gradual X% / completo]
- [ ] Smoke test pós-deploy definido — roteiro: [link] — responsável: [nome]

## 4. Produto e comunicação

- [ ] PO validou a versão candidata em homologação
- [ ] Release notes / changelog prontos
- [ ] Áreas impactadas comunicadas (suporte, comercial, clientes se aplicável)
- [ ] Documentação de usuário atualizada (quando aplicável)

---

## Decisão

**[🟢 GO / 🔴 NO-GO / 🟡 GO condicional]**

**Condições/observações:** [ex.: GO condicionado à correção do BUG-124 antes do deploy]

**Riscos aceitos e por quem:** [...]

| Papel | Nome | Decisão | Data |
| --- | --- | :---: | --- |
| QA | [Nome] | ⬜ | [DD/MM] |
| Dev/Tech Lead | [Nome] | ⬜ | [DD/MM] |
| Product Owner | [Nome] | ⬜ | [DD/MM] |

---

## Pós-deploy (preencher após a release)

- [ ] Smoke test em produção executado com sucesso — [HH:MM]
- [ ] Monitoramento sem anomalias na primeira [hora / 24h]
- [ ] Incidentes: [nenhum / links]
