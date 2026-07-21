# 🧪 Caso de Teste

> **Como usar:** copie este template para cada caso de teste complexo que mereça documentação detalhada. Para casos simples, a tabela resumida do [plano de teste](plano-de-teste.md) é suficiente.

---

## [CT-000] — [Título curto e descritivo do cenário]

| Campo | Informação |
| --- | --- |
| **ID** | [CT-000] |
| **Funcionalidade** | [Módulo/funcionalidade testada] |
| **História/Requisito** | [link para Jira, Azure DevOps, etc.] |
| **Tipo** | [Funcional / Integração / Regressão / API / ...] |
| **Prioridade** | [Alta / Média / Baixa] |
| **Automatizável?** | [Sim / Não / Já automatizado — link do script] |
| **Autor** | [Nome do QA] |
| **Data de criação** | [DD/MM/AAAA] |

---

## Objetivo

*Uma frase: o que este caso valida e por quê.*

Ex.: Garantir que um usuário com credenciais válidas consiga se autenticar e seja direcionado à página inicial.

## Pré-condições

- [Usuário cadastrado com perfil X e status ativo]
- [Ambiente de homologação disponível na versão Y]
- [Massa de dados: pedido nº 123 em status "aguardando pagamento"]

## Dados de teste

| Campo | Valor |
| --- | --- |
| [E-mail] | [usuario.teste@exemplo.com] |
| [Senha] | [onde obter — nunca registrar senha real aqui] |

## Passos e resultados esperados

| # | Passo | Resultado esperado |
| :---: | --- | --- |
| 1 | [Acessar a URL de login] | [Tela de login exibida com campos e-mail e senha] |
| 2 | [Preencher e-mail e senha válidos] | [Campos aceitam a entrada, sem mensagens de erro] |
| 3 | [Clicar em "Entrar"] | [Loading exibido; usuário redirecionado à home em até Xs] |
| 4 | [Verificar o cabeçalho da home] | [Nome do usuário logado exibido no canto superior] |

## Pós-condições

- [Sessão do usuário criada; registro de acesso gravado no log de auditoria]

---

## Execução

| Campo | Informação |
| --- | --- |
| **Executado por** | [Nome] |
| **Data da execução** | [DD/MM/AAAA] |
| **Ambiente / versão** | [homolog — release/1.4.0] |
| **Status** | ⬜ Não executado · ✅ Passou · ❌ Falhou · 🚫 Bloqueado |
| **Defeito relacionado** | [link do bug, se falhou] |
| **Evidências** | [prints, vídeo ou link da ferramenta] |

**Observações:** [comportamentos notados que não constituem falha, dúvidas levantadas, etc.]
