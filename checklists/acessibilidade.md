# ♿ Checklist — Acessibilidade (WCAG)

> **Como usar:** validações que o QA consegue fazer sem ferramentas especializadas, organizadas por esforço. Referência: [WCAG 2.2](https://www.w3.org/WAI/WCAG22/quickref/) níveis A e AA. Para auditoria formal, envolva especialista em acessibilidade.

---

## Teclado (sem usar o mouse)

- [ ] Todos os elementos interativos são alcançáveis via Tab, em ordem lógica
- [ ] O foco é sempre visível (contorno/destaque no elemento atual)
- [ ] Enter/Espaço ativam botões e links; Esc fecha modais
- [ ] Nenhuma "armadilha de teclado" — sempre é possível sair de um componente com Tab/Esc
- [ ] Ao abrir um modal, o foco vai para ele; ao fechar, volta ao elemento de origem
- [ ] Funcionalidades de hover (tooltips, menus) também funcionam via teclado

## Conteúdo e semântica

- [ ] Imagens informativas têm texto alternativo descritivo; decorativas têm alt vazio
- [ ] Títulos seguem hierarquia (h1 → h2 → h3, sem pular níveis)
- [ ] Links fazem sentido fora de contexto — evitar "clique aqui"
- [ ] Campos de formulário têm label associado (clicar no label foca o campo)
- [ ] Mensagens de erro são associadas ao campo e anunciadas (não apenas cor)
- [ ] Idioma da página declarado (`lang="pt-BR"`)
- [ ] Tabelas de dados têm cabeçalhos (`th`) corretos

## Visual

- [ ] Contraste de texto ≥ 4,5:1 (texto normal) e ≥ 3:1 (texto grande) — validar com [Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [ ] Informação nunca é transmitida **apenas** por cor (ex.: erro só em vermelho)
- [ ] Zoom do navegador a 200% não quebra o layout nem esconde conteúdo
- [ ] Textos redimensionam sem sobreposição
- [ ] Animações podem ser pausadas; nada pisca mais de 3 vezes por segundo

## Leitor de tela (teste básico)

*VoiceOver (macOS/iOS, nativo), NVDA (Windows, gratuito) ou TalkBack (Android, nativo).*

- [ ] Fluxo principal completável usando apenas o leitor de tela
- [ ] Botões com ícone (sem texto) são anunciados com nome significativo
- [ ] Estados são anunciados (selecionado, expandido, carregando, erro)
- [ ] Conteúdo dinâmico (toasts, validações) é anunciado quando aparece

## Ferramentas de apoio

| Ferramenta | Uso |
| --- | --- |
| [Lighthouse](https://developer.chrome.com/docs/lighthouse) (Chrome DevTools) | Auditoria automática de acessibilidade — bom ponto de partida |
| [axe DevTools](https://www.deque.com/axe/devtools/) | Extensão que aponta violações WCAG com explicação |
| [WAVE](https://wave.webaim.org/) | Visualização de problemas direto na página |

> ⚠️ Ferramentas automáticas cobrem ~30–40% dos critérios WCAG. O restante (ordem de foco, sentido dos textos alternativos, uso real com leitor de tela) exige verificação manual.
