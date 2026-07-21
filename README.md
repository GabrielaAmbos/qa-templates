# 📌 QA Templates

Coleção de templates em português para profissionais de qualidade de software, como planos de teste, relatórios, checklists e documentos de processo, prontos para copiar e adaptar ao seu projeto.

## Objetivo

Padronizar e acelerar a documentação de QA: em vez de começar do zero a cada projeto, copie o template, substitua os campos entre `[colchetes]` e remova o que não se aplicar. Cada template traz instruções de preenchimento e exemplos práticos.

## Como usar

1. Navegue pelo índice abaixo e abra o template desejado
2. Copie o arquivo `.md` para o seu projeto (ou para a sua ferramenta, como Confluence, Notion ou Jira)
3. Substitua os campos entre `[colchetes]` e apague as instruções em *itálico*
4. Remova seções que não se aplicam. Template bom é o que o time realmente preenche

---

## 📚 Índice de Templates

### 📄 Documentação de Testes

| Template | Descrição | Quando usar |
| --- | --- | --- |
| [Plano de Teste](documentacao/plano-de-teste.md) | Planejamento completo: escopo, estratégia, critérios de entrada/saída, riscos e cronograma | No início do ciclo de testes de uma funcionalidade ou release |
| [Caso de Teste](documentacao/caso-de-teste.md) | Caso individual detalhado: pré-condições, dados, passos e resultados esperados | Para cenários complexos que merecem documentação própria |
| [Caso de Teste em BDD](documentacao/caso-de-teste-bdd.md) | Cenários em Gherkin (Dado/Quando/Então) com guia de escrita e boas práticas | Para especificar critérios de aceite com PO e Dev, ou preparar automação com Cucumber |
| [Caso de Teste de API/Integração](documentacao/caso-de-teste-integracao.md) | Teste manual de integração validando API, banco de dados, mensageria, consumidores e logs | Quando a ação testada atravessa várias camadas e sistemas |
| [Relatório de Bug](documentacao/relatorio-de-bug.md) | Registro de defeito reproduzível: passos, evidências, severidade × prioridade | Sempre que encontrar um defeito |
| [Relatório de Execução](documentacao/relatorio-de-execucao.md) | Fechamento de ciclo: métricas, defeitos, riscos residuais e parecer final | Ao final de cada sprint, ciclo ou release |
| [Matriz de Rastreabilidade](documentacao/matriz-rastreabilidade.md) | Mapa requisito → caso de teste → defeito, com visão de cobertura | Para garantir que nenhum requisito ficou sem teste |

### 🏃 Testes Ágeis e Exploratórios

| Template | Descrição | Quando usar |
| --- | --- | --- |
| [Charter de Teste Exploratório](ageis/charter-exploratorio.md) | Sessão exploratória com missão, timebox, anotações e debriefing (SBTM) | Para explorar áreas novas ou de risco além dos casos roteirizados |
| [Definition of Ready & Done](ageis/definition-of-done.md) | Critérios de qualidade para histórias entrarem e saírem da sprint | Ao formar um time novo ou revisar o processo nas retrospectivas |

### ✔️ Checklists Práticos

| Template | Descrição | Quando usar |
| --- | --- | --- |
| [Formulários](checklists/formularios.md) | Validações de campos, comportamento, segurança básica e persistência | Em qualquer tela com entrada de dados |
| [Acessibilidade](checklists/acessibilidade.md) | Teclado, semântica, contraste e leitor de tela, baseado na WCAG 2.2 | Para validar que o produto é utilizável por todas as pessoas |
| [Segurança Básica](checklists/seguranca-basica.md) | Autenticação, autorização, exposição de dados e entradas maliciosas ao alcance do QA | Em fluxos com login, dados sensíveis ou permissões |
| [Mobile](checklists/mobile.md) | Interrupções, conectividade, hardware, instalação e matriz de dispositivos | Ao testar apps nativos, híbridos ou web mobile |

### 🤖 Automação

| Template | Descrição | Quando usar |
| --- | --- | --- |
| [Plano de Automação](automacao/plano-de-automacao.md) | Estratégia: o que automatizar, pirâmide de testes, ferramentas e métricas | Antes de iniciar (ou reorganizar) a automação do projeto |
| [Teste de API](automacao/teste-de-api.md) | Especificação por endpoint: contrato, casos de sucesso, erro e borda | Ao testar APIs REST manualmente ou especificar automação |

### ⚙️ Processo e Gestão

| Template | Descrição | Quando usar |
| --- | --- | --- |
| [Go/No-Go de Release](processo/go-no-go-release.md) | Checklist de decisão de deploy: qualidade, técnica, operação e rollback | Na reunião de aprovação de cada release |
| [Post-mortem de Defeito](processo/post-mortem-defeito.md) | Análise blameless de bug em produção: linha do tempo, 5 porquês e ações | Quando um defeito relevante escapa para produção |
| [Métricas de Qualidade](processo/metricas-de-qualidade.md) | Relatório periódico: taxa de escape, defeitos, execução e automação | Mensalmente ou por sprint, para acompanhar tendências |

---

## 🔗 Referências oficiais

- [ISTQB](https://istqb.org/: certificações e [glossário oficial de termos de teste](https://glossary.istqb.org/)
- [BSTQB](https://bstqb.org.br/): braço brasileiro do ISTQB, com syllabi traduzidos
- [ISO/IEC 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010): modelo de características de qualidade de software
- [WCAG 2.2 (W3C)](https://www.w3.org/WAI/WCAG22/quickref/) — diretrizes de acessibilidade para conteúdo web
- [OWASP Top 10](https://owasp.org/www-project-top-ten/): principais riscos de segurança em aplicações web
- [The Practical Test Pyramid — Martin Fowler](https://martinfowler.com/articles/practical-test-pyramid.html): estratégia de automação por camadas
- [Ministry of Testing](https://www.ministryoftesting.com/): comunidade global de testes de software

## 🤝 Contribuindo

Sugestões e melhorias são bem-vindas: abra uma issue descrevendo o problema/ideia ou envie um pull request. Ao propor um novo template, siga o padrão dos existentes:  instruções de uso no topo, campos em `[colchetes]` e exemplos preenchidos.

## 📄 Licença

Livre para usar e adaptar nos seus projetos.
