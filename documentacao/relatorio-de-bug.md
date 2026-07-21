# 🐞 Relatório de Bug

> **Como usar:** copie este template ao abrir um defeito na sua ferramenta (Jira, Azure DevOps, GitHub Issues). Um bom relatório permite que qualquer pessoa reproduza o problema sem falar com você.

---

## Título

*Formato sugerido: `[Módulo] Ação → resultado incorreto`. Seja específico.*

- ❌ "Erro no login"
- ✅ "[Login] Autenticação com e-mail em maiúsculas retorna erro 500"

---

## Descrição

| Campo | Informação |
| --- | --- |
| **Severidade** | [🔴 Crítica / 🟠 Alta / 🟡 Média / 🟢 Baixa] |
| **Prioridade** | [Urgente / Alta / Média / Baixa — definida com o PO] |
| **Ambiente** | [Produção / Homologação / Desenvolvimento] |
| **Versão / branch** | [release/1.4.0 — commit abc1234] |
| **SO / dispositivo** | [Windows 11 / iPhone 15 iOS 17] |
| **Navegador** | [Chrome 126] |
| **Usuário utilizado** | [perfil/permissões — não incluir senha] |
| **Frequência** | [Sempre / Intermitente (X em Y tentativas)] |
| **Caso de teste relacionado** | [CT-000, se aplicável] |

### Passos para reproduzir

1. [Acessar a tela X]
2. [Preencher o campo Y com o valor Z]
3. [Clicar em "Confirmar"]

### Resultado obtido

[O que aconteceu de fato — inclua a mensagem de erro exata, código HTTP, comportamento visual.]

### Resultado esperado

[O que deveria acontecer, com referência ao requisito/critério de aceite quando existir.]

### Evidências

- [Print ou vídeo do erro]
- [Log do console / resposta da API / stack trace]
- [HAR file ou request/response, se problema de rede]

### Informações adicionais

- **Workaround conhecido:** [existe caminho alternativo? qual?]
- **Impacto:** [quem é afetado e em que escala — ex.: todos os usuários mobile]
- **Suspeita de causa:** [opcional — só se tiver embasamento]

---

## Guia rápido de severidade

| Severidade | Definição |
| --- | --- |
| 🔴 Crítica | Bloqueia o uso da funcionalidade, causa perda de dados ou afeta produção sem contorno |
| 🟠 Alta | Fluxo principal comprometido, sem alternativa de contorno |
| 🟡 Média | Fluxo comprometido, mas com alternativa de contorno |
| 🟢 Baixa | Problema visual ou de usabilidade sem impacto funcional |

> **Severidade ≠ prioridade:** severidade mede o impacto técnico (definida pelo QA); prioridade mede a urgência de correção (definida com o PO). Um bug crítico em uma feature pouco usada pode ter prioridade baixa.
