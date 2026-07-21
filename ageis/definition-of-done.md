# ✅ Definition of Ready & Definition of Done (foco em qualidade)

> **Como usar:** adapte com o time — DoR e DoD só funcionam quando acordados por todos (não impostos pelo QA). Revise a cada retrospectiva. Remova itens que o time ainda não consegue cumprir; um checklist ignorado é pior que um checklist curto.

---

## Definition of Ready (DoR)

*Uma história só entra na sprint quando:*

- [ ] Critérios de aceite escritos e revisados (formato sugerido: Given/When/Then)
- [ ] Cenários de exceção e regras de negócio descritos (não só o caminho feliz)
- [ ] Protótipo/design aprovado e linkado (quando envolve UI)
- [ ] Dependências externas identificadas (APIs, outros times, dados)
- [ ] Impacto em funcionalidades existentes mapeado (candidatas a regressão)
- [ ] História estimada e cabível em uma sprint
- [ ] QA participou do refinamento (three amigos: PO + Dev + QA)

---

## Definition of Done (DoD)

*Uma história só é considerada pronta quando:*

### Desenvolvimento

- [ ] Código revisado (code review aprovado)
- [ ] Testes unitários escritos e passando
- [ ] Build passando no CI, sem novos warnings relevantes
- [ ] Migrações e configurações documentadas

### Qualidade

- [ ] Todos os critérios de aceite validados pelo QA
- [ ] Casos de teste executados e evidenciados — [link da ferramenta]
- [ ] Regressão dos fluxos impactados executada
- [ ] Nenhum defeito crítico ou alto em aberto
- [ ] Defeitos médios/baixos registrados e priorizados com o PO
- [ ] Testes automatizados atualizados (quando o fluxo é coberto pela automação)

### Produto

- [ ] Validada pelo PO em ambiente de homologação
- [ ] Documentação de usuário atualizada (quando aplicável)
- [ ] Feature flag / plano de rollout definido (quando aplicável)

---

## DoD de release (além do DoD de história)

- [ ] Suíte de regressão completa executada
- [ ] [Checklist de go/no-go](../processo/go-no-go-release.md) preenchido
- [ ] Plano de rollback definido e testado
- [ ] Monitoramento e alertas configurados para as novas funcionalidades
