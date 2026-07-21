# 🥒 Caso de Teste em BDD (Gherkin)

> **Como usar:** escreva os cenários em linguagem Gherkin (Dado/Quando/Então) durante o refinamento, junto com PO e Dev — o valor do BDD está na **conversa antes do código**, não apenas na sintaxe. Os cenários servem como critérios de aceite vivos e, se o projeto usar Cucumber/SpecFlow/Behave, viram automação diretamente.

---

## Funcionalidade: [Nome da funcionalidade]

| Campo | Informação |
| --- | --- |
| **História/Requisito** | [link para Jira, Azure DevOps, etc.] |
| **Autor** | [Nome] — escrito com: [PO, Dev — three amigos] |
| **Data** | [DD/MM/AAAA] |
| **Automatizado?** | [Sim — link do feature file no repo / Não / Planejado] |

---

## Estrutura do arquivo `.feature`

```gherkin
# language: pt

Funcionalidade: Aplicação de cupom de desconto no checkout
  Como cliente da loja
  Quero aplicar um cupom de desconto no meu pedido
  Para pagar mais barato na finalização da compra

  Contexto:
    Dado que estou autenticado como cliente
    E tenho um carrinho com produtos somando R$ 200,00

  Cenário: Aplicar cupom válido de percentual
    Dado que existe o cupom "PROMO10" de 10% de desconto ativo
    Quando aplico o cupom "PROMO10" no checkout
    Então o desconto de "R$ 20,00" é exibido no resumo
    E o valor total do pedido é "R$ 180,00"

  Cenário: Aplicar cupom expirado
    Dado que existe o cupom "NATAL23" expirado em "25/12/2023"
    Quando aplico o cupom "NATAL23" no checkout
    Então vejo a mensagem "Este cupom não está mais válido"
    E o valor total do pedido permanece "R$ 200,00"

  Esquema do Cenário: Validação de cupons em diferentes situações
    Dado que existe o cupom "<cupom>" na situação "<situacao>"
    Quando aplico o cupom "<cupom>" no checkout
    Então vejo a mensagem "<mensagem>"

    Exemplos:
      | cupom    | situacao              | mensagem                            |
      | USADO1X  | já utilizado          | Este cupom já foi utilizado         |
      | OUTROUSER| de outro usuário      | Cupom não disponível para sua conta |
      | MINIMO   | abaixo do valor mínimo| Pedido mínimo de R$ 300,00          |
```

---

## Guia rápido de escrita

### Palavras-chave (português)

| Palavra | Uso |
| --- | --- |
| `Funcionalidade` | O que está sendo especificado, com a narrativa Como/Quero/Para |
| `Contexto` | Passos comuns a todos os cenários (executa antes de cada um) |
| `Cenário` | Um comportamento específico, com nome descritivo |
| `Dado` (Given) | Estado inicial — o mundo antes da ação |
| `Quando` (When) | A ação do usuário/sistema — idealmente **uma só** por cenário |
| `Então` (Then) | O resultado observável e verificável |
| `E` / `Mas` | Continuação do passo anterior |
| `Esquema do Cenário` + `Exemplos` | Mesmo fluxo com variação de dados (tabela) |

### Boas práticas

- ✅ **Linguagem de negócio, não de interface:** "Quando aplico o cupom" em vez de "Quando clico no botão #apply-coupon"
- ✅ **Cenário curto:** 3–6 passos; se passar disso, provavelmente são dois cenários
- ✅ **Um comportamento por cenário:** um `Quando` e um resultado principal
- ✅ **Declarativo, não imperativo:** esconda detalhes de execução que não importam para a regra
- ✅ **Título do cenário descreve a regra:** "Aplicar cupom expirado", não "Teste 2"
- ❌ Evite cenários dependentes entre si — cada um deve rodar isolado
- ❌ Evite detalhes técnicos (SQL, seletores, endpoints) no Gherkin — isso vive nos steps de automação

### Checklist de cobertura da funcionalidade

- [ ] Caminho feliz coberto
- [ ] Cenários de exceção e mensagens de erro
- [ ] Regras de negócio com limites (valor mínimo, datas, quantidades) — bom uso de `Esquema do Cenário`
- [ ] Comportamento por perfil/permissão (quando aplicável)
- [ ] Cenários revisados por PO e Dev (three amigos)
