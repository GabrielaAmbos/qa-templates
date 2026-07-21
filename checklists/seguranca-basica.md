# 🔒 Checklist — Segurança Básica

> **Como usar:** validações de segurança ao alcance do QA, sem exigir perfil de pentester. Não substitui pentest nem análise de vulnerabilidade formal — encontrou algo suspeito, reporte com evidência e envolva o time de segurança. Referência: [OWASP Top 10](https://owasp.org/www-project-top-ten/).

> ⚠️ Execute estes testes **apenas** em ambientes do seu próprio projeto e com autorização do time.

---

## Autenticação

- [ ] Senha nunca aparece em texto claro (tela, URL, logs do console, resposta de API)
- [ ] Mensagem de login inválido é genérica — não revela se o erro foi no e-mail ou na senha
- [ ] Política de senha aplicada no backend (não apenas validação visual no front)
- [ ] Bloqueio ou atraso progressivo após N tentativas falhas de login
- [ ] Logout invalida a sessão — voltar com o botão "voltar" não restaura a área logada
- [ ] Sessão expira após inatividade conforme requisito
- [ ] Link de recuperação de senha expira e só funciona uma vez

## Autorização

- [ ] URLs de áreas restritas acessadas sem login redirecionam para autenticação
- [ ] Usuário do perfil X não acessa telas/ações do perfil Y digitando a URL direta
- [ ] IDs na URL trocados manualmente (`/pedidos/123` → `/pedidos/124`) não expõem dados de outro usuário (IDOR)
- [ ] Ações restritas escondidas na interface também são bloqueadas na API (testar via Postman/DevTools)

## Exposição de dados

- [ ] Respostas de API não retornam campos além do necessário (senha, tokens, dados de outros usuários)
- [ ] Mensagens de erro não expõem stack trace, versão de framework ou SQL
- [ ] Dados sensíveis (CPF, cartão) mascarados na exibição quando não precisam aparecer completos
- [ ] Todo o tráfego usa HTTPS; requisições HTTP redirecionam
- [ ] Dados sensíveis não ficam em query string, localStorage sem necessidade, nem em logs

## Entradas maliciosas (teste com moderação)

- [ ] XSS: `<script>alert(1)</script>` e `<img src=x onerror=alert(1)>` em campos de texto são exibidos como texto, nunca executados
- [ ] SQL injection: `' OR '1'='1` e `'; --` em campos e filtros não causam erro 500 nem retorno anômalo de dados
- [ ] Upload de arquivos: extensões perigosas (.exe, .html, .svg com script) são rejeitadas; validação por conteúdo, não só extensão; limite de tamanho aplicado
- [ ] Campos numéricos com valores extremos (negativos, zero, muito grandes) tratados sem quebra

## Sinais de alerta para reportar imediatamente

- Token/senha visível em URL ou logs
- Dados de outro usuário retornados em qualquer situação
- Erro 500 com stack trace exposto ao usuário final
- Área restrita acessível sem autenticação
