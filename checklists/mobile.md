# 📱 Checklist — Testes Mobile

> **Como usar:** aplique a apps nativos e híbridos; boa parte também vale para web mobile. Priorize os dispositivos conforme a base real de usuários do produto (analytics) — não conforme os aparelhos disponíveis na mesa.

---

## Matriz de dispositivos

*Defina antes de começar. Exemplo:*

| Dispositivo | SO | Tela | Prioridade | Por quê |
| --- | --- | --- | :---: | --- |
| [Samsung Galaxy A15] | [Android 14] | [6.5"] | Alta | [Android mais comum na base — X%] |
| [iPhone 13] | [iOS 17] | [6.1"] | Alta | [iOS mais comum na base — Y%] |
| [Motorola Moto E] | [Android 12] | [6.0"] | Média | [Aparelho de entrada — performance] |

## Interrupções

- [ ] Receber ligação durante o uso: app retorna ao estado anterior sem perda de dados
- [ ] Notificação push de outro app durante um fluxo crítico não quebra o fluxo
- [ ] Alarme/despertador disparando durante o uso
- [ ] Minimizar o app no meio de um formulário e retornar: dados preservados
- [ ] App em segundo plano por longo período: reabre sem crash (sessão pode expirar com mensagem adequada)
- [ ] Bateria fraca / modo de economia de energia: app continua funcional

## Conectividade

- [ ] Modo avião no meio de uma ação: mensagem clara, sem crash nem estado inconsistente
- [ ] Rede lenta (3G) : loadings adequados, sem duplicação de requisições
- [ ] Alternância Wi-Fi ↔ dados móveis durante o uso
- [ ] Reconexão: ação interrompida pode ser retomada ou refeita sem efeito duplicado (ex.: pagamento não cobra duas vezes)
- [ ] Comportamento offline conforme requisito (cache, fila de sincronização ou bloqueio com aviso)

## Hardware e sistema

- [ ] Rotação de tela (retrato ↔ paisagem) não quebra layout nem perde dados — ou bloqueio de rotação intencional
- [ ] Permissões (câmera, localização, notificações): fluxo de negar → usar a funcionalidade → conceder depois
- [ ] Permissão negada permanentemente: app orienta a habilitar nas configurações
- [ ] Botão físico/gesto de voltar (Android): comportamento consistente, sem sair do app inesperadamente
- [ ] Teclado: não cobre o campo em foco; fecha adequadamente; tipo correto por campo (numérico, e-mail)
- [ ] Diferentes tamanhos de tela e notch: conteúdo não é cortado
- [ ] Modo escuro (se suportado): telas legíveis em ambos os temas
- [ ] Fonte do sistema ampliada (acessibilidade): layout não quebra

## Instalação e atualização

- [ ] Instalação limpa funciona (primeiro uso, onboarding)
- [ ] Atualização de versão anterior preserva dados e sessão do usuário
- [ ] Desinstalar e reinstalar: comportamento de dados conforme esperado
- [ ] Versão mínima de SO respeitada — aparelhos abaixo não recebem/instalam

## Específicos da plataforma

- [ ] **Android:** testar em pelo menos um aparelho de entrada (pouca RAM) — performance e crashes
- [ ] **iOS:** gestos de navegação (swipe para voltar) funcionam
- [ ] Deep links / links de notificação abrem a tela correta, logado e deslogado
