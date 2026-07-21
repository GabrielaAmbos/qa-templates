# 📋 Plano de Teste

> **Como usar este template:** faça uma cópia deste arquivo, substitua todos os campos entre `[colchetes]` pelas informações do seu projeto e remova as seções que não se aplicam. Os textos em *itálico* são instruções de preenchimento — apague-os na versão final.

---

## Plano de Testes — [Nome da Funcionalidade]

| Campo | Informação |
| --- | --- |
| **Projeto** | [Nome do projeto] |
| **Funcionalidade** | [Nome da funcionalidade ou épico] |
| **Responsável de Qualidade** | [Nome do QA] |
| **Responsável de Desenvolvimento** | [Nome do Dev] |
| **Product Owner** | [Nome do PO] |
| **Data de criação** | [DD/MM/AAAA] |
| **Versão do documento** | [1.0] |
| **Status** | [Em elaboração / Em revisão / Aprovado] |

### Histórico de Alterações

| Versão | Data | Autor | Descrição |
| ------ | ---------- | ------------ | ------------------------ |
| 1.0 | DD/MM/AAAA | [Nome do QA] | Criação do documento |

---

## 1. Objetivo

*Descreva em 2–3 frases o que este plano cobre e qual o resultado esperado.*

Ex.: Validar a funcionalidade de [X] do sistema [Y], garantindo que os fluxos principais e alternativos funcionem conforme os critérios de aceite definidos em [link da história/requisito].

**Referências:**
- História/Requisito: [link para Jira, Azure DevOps, etc.]
- Protótipo/Design: [link para Figma, etc.]
- Documentação técnica: [link]

---

## 2. Escopo

### 2.1 O que será testado

*Liste as funcionalidades e fluxos cobertos por este plano.*

- [Funcionalidade X — fluxo principal]
- [Funcionalidade X — fluxos alternativos e de exceção]
- [Integração com o sistema Y]

### 2.2 O que NÃO será testado (fora de escopo)

*Tão importante quanto o escopo: deixe explícito o que está fora, e por quê.*

- [Funcionalidade Z — será coberta no plano de teste da sprint N]
- [Teste de carga — sem infraestrutura disponível neste ciclo]

---

## 3. Estratégia e Tipos de Teste

*Marque os tipos aplicáveis e descreva brevemente a abordagem de cada um.*

| Tipo de teste | Aplicável? | Abordagem |
| --- | :---: | --- |
| Funcional | ☑ | Execução manual dos casos de teste baseados nos critérios de aceite |
| Regressão | ☑ | Reexecução da suíte [manual/automatizada] dos fluxos impactados |
| Integração | ☑ | Validação das integrações com [sistema/API X] |
| API | ☐ | Validação de contratos e respostas via [Postman/Insomnia] |
| Usabilidade | ☐ | Validação contra o protótipo aprovado no [Figma] |
| Responsividade / Cross-browser | ☐ | Navegadores: [Chrome, Firefox, Safari]; Resoluções: [desktop, mobile] |
| Performance | ☐ | [Ferramenta e critério, ex.: k6, resposta < 2s com 100 usuários] |
| Segurança | ☐ | [Ex.: validação de autenticação/autorização nos endpoints] |
| Acessibilidade | ☐ | [Ex.: navegação por teclado, leitor de tela, contraste — WCAG AA] |

---

## 4. Critérios de Entrada e Saída

### 4.1 Critérios de entrada (para iniciar os testes)

- [ ] Funcionalidade implementada e disponível no ambiente de teste
- [ ] Critérios de aceite definidos e aprovados
- [ ] Massa de dados disponível
- [ ] Acessos e permissões concedidos ao time de QA

### 4.2 Critérios de saída (para encerrar os testes)

- [ ] 100% dos casos de teste executados
- [ ] Nenhum defeito **crítico** ou **alto** em aberto
- [ ] Defeitos de severidade média/baixa registrados e priorizados com o PO
- [ ] Evidências de teste anexadas em [ferramenta]

### 4.3 Critérios de suspensão

*Condições que pausam a execução dos testes.*

- Ambiente de teste indisponível por mais de [X horas]
- Defeito bloqueador impedindo a execução dos demais casos

---

## 5. Casos de Teste

*Liste os casos de teste ou aponte para a ferramenta onde estão gerenciados (TestRail, Qase, Xray, planilha, etc.).*

**Ferramenta de gestão:** [link]

| ID | Cenário | Pré-condição | Passos | Resultado esperado | Prioridade | Status |
| --- | --- | --- | --- | --- | :---: | :---: |
| CT-001 | [Login com credenciais válidas] | [Usuário cadastrado e ativo] | [1. Acessar a tela de login<br>2. Informar e-mail e senha válidos<br>3. Clicar em "Entrar"] | [Usuário autenticado e redirecionado para a home] | Alta | ⬜ |
| CT-002 | [Login com senha inválida] | [Usuário cadastrado] | [1. Informar senha incorreta<br>2. Clicar em "Entrar"] | [Mensagem de erro exibida, sem indicar qual campo está errado] | Alta | ⬜ |
| CT-003 | [...] | [...] | [...] | [...] | Média | ⬜ |

**Legenda de status:** ⬜ Não executado · ✅ Passou · ❌ Falhou · 🚫 Bloqueado

---

## 6. Ambiente de Teste

| Item | Detalhe |
| --- | --- |
| **URL do ambiente** | [https://homolog.sistema.com] |
| **Branch/versão testada** | [ex.: release/1.4.0 — commit abc1234] |
| **Sistemas operacionais** | [Windows 11, macOS, Android 14, iOS 17] |
| **Navegadores** | [Chrome 126+, Firefox 127+, Safari 17+] |
| **Dispositivos** | [Desktop, celular — modelos se relevante] |
| **Usuários de teste** | [Onde obter: cofre de senhas, planilha X — nunca commitar credenciais] |
| **Massa de dados** | [Como gerar/obter: script, importação, cadastro manual] |

---

## 7. Gestão de Defeitos

- **Ferramenta de registro:** [Jira, Azure DevOps, GitHub Issues]
- **Template de abertura:** título, passos para reproduzir, resultado esperado × obtido, evidência (print/vídeo), ambiente e versão.

### Classificação de severidade

| Severidade | Definição | SLA de correção |
| --- | --- | --- |
| 🔴 Crítica | Bloqueia o uso da funcionalidade ou causa perda de dados | [Imediato] |
| 🟠 Alta | Fluxo principal comprometido, sem alternativa de contorno | [X dias] |
| 🟡 Média | Fluxo comprometido, mas com alternativa de contorno | [Próxima sprint] |
| 🟢 Baixa | Problema visual ou de usabilidade sem impacto funcional | [Backlog] |

---

## 8. Riscos e Mitigações

*Adapte à realidade do projeto — riscos genéricos ajudam pouco.*

| Risco | Probabilidade | Impacto | Mitigação |
| --- | :---: | :---: | --- |
| Atraso na entrega do desenvolvimento | Média | Alto | Priorizar casos críticos; renegociar prazo com o PO |
| Ambiente de teste instável | Média | Alto | Acionar [time de infra]; ter ambiente alternativo mapeado |
| Falta de massa de dados | Baixa | Médio | Preparar scripts de geração de dados antes do início |
| [Risco específico do projeto] | [...] | [...] | [...] |

---

## 9. Cronograma

| Atividade | Responsável | Início | Fim | Estimativa |
| --- | --- | --- | --- | --- |
| Elaboração do plano de teste | [QA] | [DD/MM] | [DD/MM] | [1 dia] |
| Criação dos casos de teste | [QA] | [DD/MM] | [DD/MM] | [2 dias] |
| Preparação de ambiente e massa de dados | [QA/Dev] | [DD/MM] | [DD/MM] | [1 dia] |
| Execução dos testes | [QA] | [DD/MM] | [DD/MM] | [3 dias] |
| Reteste de correções | [QA] | [DD/MM] | [DD/MM] | [1 dia] |
| Relatório final e encerramento | [QA] | [DD/MM] | [DD/MM] | [0,5 dia] |

---

## 10. Relatório de Encerramento

*Preencha ao final do ciclo de testes.*

| Métrica | Valor |
| --- | --- |
| Casos de teste planejados | [n] |
| Casos executados | [n] ([%]) |
| Casos aprovados | [n] ([%]) |
| Defeitos encontrados | [n] (críticos: [n] · altos: [n] · médios: [n] · baixos: [n]) |
| Defeitos corrigidos e retestados | [n] |

**Parecer final do QA:** [Aprovado para produção / Aprovado com ressalvas / Reprovado]

**Justificativa:** [...]

### Aprovações

| Papel | Nome | Data | Aprovado? |
| --- | --- | --- | :---: |
| QA | [Nome] | [DD/MM/AAAA] | ⬜ |
| Product Owner | [Nome] | [DD/MM/AAAA] | ⬜ |
