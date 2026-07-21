# 🤖 Plano de Automação de Testes

> **Como usar:** documento vivo da estratégia de automação do projeto — revise a cada trimestre ou mudança relevante de stack. Automação é investimento: este plano existe para decidir **o que vale automatizar** antes de discutir ferramenta.

---

## Plano de Automação — [Projeto]

| Campo | Informação |
| --- | --- |
| **Projeto** | [Nome] |
| **Responsável** | [Nome] |
| **Data / versão** | [DD/MM/AAAA — v1.0] |

---

## 1. Objetivo

*O que a automação deve entregar para este projeto.*

Ex.: Reduzir o tempo de regressão manual de [X dias] para [Y horas], cobrindo os fluxos críticos de negócio a cada release.

## 2. Critérios para automatizar (ou não)

*Avalie cada candidato a automação:*

| Critério | Automatizar se... |
| --- | --- |
| Frequência | Executado a cada release/sprint (regressão) |
| Estabilidade | Funcionalidade madura, sem redesign previsto |
| Criticidade | Falha causaria impacto grave (pagamento, login, checkout) |
| Repetitividade | Passos determinísticos, sem julgamento visual/subjetivo |
| Custo de execução manual | Demorado, tedioso ou dependente de muitos dados |

**Não automatizar (agora):** funcionalidades instáveis/em redesign, testes exploratórios, validações visuais subjetivas, fluxos executados raramente.

## 3. Estratégia por camada (pirâmide de testes)

*Referência: [The Practical Test Pyramid — Martin Fowler](https://martinfowler.com/articles/practical-test-pyramid.html)*

| Camada | Responsável | Ferramenta | Cobertura-alvo | O que cobre |
| --- | --- | --- | --- | --- |
| Unitários | Devs | [Jest / JUnit / pytest] | [70–80% do código novo] | Regras de negócio isoladas |
| Integração / API | [Devs + QA] | [Supertest / RestAssured / Postman+Newman] | [Endpoints críticos] | Contratos, status, regras entre serviços |
| E2E (interface) | QA | [Playwright / Cypress / Appium] | [Somente fluxos críticos] | Jornadas completas do usuário |

> Regra prática: se dá para testar na camada de baixo, não suba. E2E é a camada mais cara e mais frágil — reserve para jornadas de negócio.

## 4. Escopo inicial (primeiros ciclos)

| Prioridade | Fluxo | Camada | Justificativa |
| :---: | --- | --- | --- |
| 1 | [Login e recuperação de senha] | E2E | [Porta de entrada — bloqueia tudo] |
| 2 | [Checkout completo] | E2E + API | [Receita direta] |
| 3 | [CRUD de X] | API | [Alta frequência de regressão] |

## 5. Definições técnicas

- **Padrões de projeto:** [Page Objects / Screenplay; convenção de nomes; estrutura de pastas]
- **Massa de dados:** [criada via API/factory antes de cada teste — nunca dependente de dados pré-existentes do ambiente]
- **Execução no CI:** [pipeline, gatilho (PR? nightly?), paralelização, retries]
- **Relatórios:** [Allure / relatório nativo — onde ficam publicados]
- **Critério de flaky:** [teste que falha intermitentemente é quarentenado e corrigido em até X dias — nunca ignorado silenciosamente]

## 6. Métricas de acompanhamento

| Métrica | Meta |
| --- | --- |
| Cobertura dos fluxos críticos por automação | [100% dos fluxos P1] |
| Tempo de execução da suíte | [< X min no CI] |
| Taxa de testes flaky | [< 2%] |
| Bugs de regressão pegos pela automação vs. manual | [acompanhar tendência] |

## 7. Riscos

| Risco | Mitigação |
| --- | --- |
| Suíte E2E lenta/frágil vira gargalo do CI | Limitar E2E aos fluxos críticos; empurrar cobertura para API |
| Automação desatualizada vira "suíte que ninguém olha" | Quebrou → corrigir na hora ou quarentenar com prazo; falha de teste bloqueia merge |
| Conhecimento concentrado em uma pessoa | Code review dos testes; documentação de setup |
