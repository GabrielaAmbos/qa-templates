# 🧭 Charter de Teste Exploratório (Session-Based Testing)

> **Como usar:** um charter por sessão de teste exploratório. Defina a missão e o timebox **antes** de começar; preencha as anotações **durante** a sessão; feche com o debriefing logo após. Sessões típicas duram de 60 a 120 minutos, sem interrupções.

---

## Charter — [Sessão nº X]

| Campo | Informação |
| --- | --- |
| **Missão** | Explorar [área/funcionalidade] usando [recursos/dados] para descobrir [tipo de problema] |
| **Testador** | [Nome] |
| **Data** | [DD/MM/AAAA] |
| **Timebox** | [90 min] — início: [HH:MM] · fim: [HH:MM] |
| **Ambiente / versão** | [homolog — release/1.4.0] |
| **Prioridade da sessão** | [Alta / Média / Baixa] |

**Exemplo de missão:** Explorar o fluxo de checkout usando cupons de desconto expirados, inválidos e acumulados para descobrir problemas de cálculo de valores.

### Áreas a explorar (guia, não roteiro)

- [Combinações de cupom + frete grátis]
- [Alteração do carrinho após aplicar o cupom]
- [Comportamento com sessão expirada no meio do fluxo]

### Fora do escopo desta sessão

- [Pagamento com cartão — coberto na sessão nº Y]

---

## Anotações da sessão

*Registre em tempo real: o que testou, o que observou, ideias que surgiram.*

| Hora | Anotação | Tipo |
| --- | --- | :---: |
| [HH:MM] | [Apliquei cupom expirado → mensagem genérica "erro no servidor"] | 🐞 Bug |
| [HH:MM] | [Cupom aplicado permanece após esvaziar o carrinho — verificar se é esperado] | ❓ Dúvida |
| [HH:MM] | [Testar o mesmo fluxo no mobile em outra sessão] | 💡 Ideia |

**Legenda:** 🐞 Bug encontrado · ❓ Dúvida/questão para o time · 💡 Ideia para nova sessão ou caso de teste · ⚠️ Risco observado

---

## Debriefing (preencher ao final)

| Métrica | Valor |
| --- | --- |
| Tempo em teste (T) | [%] — *testando de fato* |
| Tempo em investigação de bug (B) | [%] — *reproduzindo/documentando bugs* |
| Tempo em setup (S) | [%] — *preparando ambiente/dados* |
| Bugs encontrados | [n] — [links dos registros] |
| Dúvidas levantadas | [n] |
| Novas sessões sugeridas | [n] |

### Resumo

- **A missão foi cumprida?** [Sim / Parcialmente — o que faltou]
- **Impressão geral da qualidade da área explorada:** [...]
- **Próximos passos:** [novas sessões, casos de teste a formalizar, conversas com o time]
