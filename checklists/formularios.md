# 📝 Checklist — Formulários

> **Como usar:** aplique a qualquer tela com entrada de dados (cadastro, login, checkout, filtros). Marque N/A no que não se aplicar. Itens genéricos propositalmente — some a eles as regras de negócio específicas do seu formulário.

---

## Campos e validações

- [ ] Campos obrigatórios impedem o envio quando vazios, com mensagem clara junto ao campo
- [ ] Mensagens de erro indicam **qual** campo falhou e **como** corrigir
- [ ] Limites de caracteres (mínimo e máximo) validados — o que acontece no limite exato?
- [ ] Campos numéricos rejeitam letras e símbolos; aceitam apenas o formato esperado
- [ ] Campos com máscara (CPF, telefone, CEP, data) formatam e validam corretamente
- [ ] E-mail validado quanto ao formato (`a@b.c`) — inclusive com espaços antes/depois
- [ ] Espaços no início/fim são tratados (trim) antes de salvar
- [ ] Caracteres especiais e acentos são aceitos e persistidos corretamente (ção, ü, emoji 🙂)
- [ ] Copiar e colar funciona nos campos (inclusive senha, salvo requisito contrário)
- [ ] Valores pré-preenchidos/padrão estão corretos

## Comportamento do formulário

- [ ] Duplo clique no botão de envio não cria registro duplicado
- [ ] Botão de envio desabilitado/loading durante o processamento
- [ ] Dados preenchidos não se perdem ao errar um campo e corrigir
- [ ] Comportamento ao atualizar a página (F5) no meio do preenchimento é aceitável
- [ ] Navegação por teclado: Tab percorre os campos em ordem lógica; Enter envia
- [ ] Mensagem de sucesso confirma o envio e indica o próximo passo
- [ ] Cancelar/voltar não salva dados e (idealmente) avisa sobre perda de alterações

## Segurança básica

- [ ] Entradas com HTML/script (`<script>alert(1)</script>`) são exibidas como texto, não executadas
- [ ] Entradas com aspas e SQL (`' OR 1=1 --`) não causam erro 500 nem comportamento estranho
- [ ] Campos de senha ocultam o valor e não aparecem na URL nem em logs
- [ ] Dados sensíveis trafegam via HTTPS e não aparecem em query string

## Persistência e integração

- [ ] Dados salvos aparecem corretamente ao reabrir/editar o registro
- [ ] Edição preserva os campos não alterados
- [ ] Registro criado reflete nas listagens, buscas e relatórios relacionados
- [ ] Comportamento em falha da API (timeout, 500): mensagem amigável, sem perda dos dados digitados

## Apresentação

- [ ] Labels, placeholders e textos sem erros de português
- [ ] Layout íntegro nas resoluções-alvo (desktop, tablet, mobile)
- [ ] Estados visuais: foco, erro, desabilitado e loading claramente distintos
