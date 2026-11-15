## Cenário 25: Configurações da academia na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de configurações.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C25-CT01 | Verificar se a tela de configurações é exibida com o resumo e as abas. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                 |
| :----------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                 |
| **QUANDO** acessarmos o menu "Configurações"                                                                                               |
| **ENTÃO** a tela deverá exibir os cards de resumo (Desktop, Presença, Avaliação e SifitBox) com os mesmos valores dos campos da aba "Home" |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O resumo deve ser coerente com as configurações salvas. |

| **Resultado da execução**                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Os cards exibiram Desktop "Sim", Presença "Check-in", Avaliação "Bioimpedância" e SifitBox "Sim", iguais aos campos. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Navegação entre as abas de configurações.

| ID       | Descrição                                   |
| :------- | :------------------------------------------ |
| C25-CT02 | Verificar se cada aba exibe os seus campos. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de configurações                                                          |
| **QUANDO** clicarmos nas abas Home, Biometria, Avaliação, Aniversário, Pagamento, Integrações e Design |
| **ENTÃO** cada aba deverá exibir os seus campos                                                        |

| **Critérios de aceitação**          |
| :---------------------------------- |
| Todas as abas devem abrir sem erro. |

| **Resultado da execução**                                |
| :------------------------------------------------------- |
| **Passou.** As 7 abas abriram e exibiram os seus campos. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Cancelar alteração das configurações.

| ID       | Descrição                                             |
| :------- | :---------------------------------------------------- |
| C25-CT03 | Verificar se o botão "Cancelar" descarta a alteração. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que alteramos "Dias para contar cliente como ausente" de 120 para 99 |
| **QUANDO** clicarmos no botão "Cancelar" e voltarmos ao menu "Configurações"  |
| **ENTÃO** o campo deverá continuar com 120                                    |

| **Critérios de aceitação**                  |
| :------------------------------------------ |
| A alteração não deve ser salva ao cancelar. |

| **Resultado da execução**                                                                              |
| :----------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema voltou para a Página Inicial sem salvar; ao reabrir, o campo continuava com 120. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Confirmação ao salvar as configurações.

| ID       | Descrição                                     |
| :------- | :-------------------------------------------- |
| C25-CT04 | Verificar se o sistema confirma o salvamento. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de configurações                         |
| **QUANDO** clicarmos no botão "Salvar Configurações" sem alterar nada |
| **ENTÃO** o sistema deverá exibir uma mensagem de sucesso             |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| O usuário deve receber confirmação de que as configurações foram salvas. |

| **Resultado da execução**                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Nenhuma mensagem é exibida. No DevTools, o servidor responde sem erro, mas a tela não informa que salvou. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Dias para cliente ausente com valor negativo.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C25-CT05 | Verificar se o sistema rejeita um número de dias negativo. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que informamos "-5" em "Dias para contar cliente como ausente"              |
| **QUANDO** clicarmos no botão "Salvar Configurações"                                 |
| **ENTÃO** o sistema deverá informar que o valor deve ser maior que zero e não salvar |
| **E** ao final, voltamos o campo para 120 e salvamos                                 |

| **Critérios de aceitação**               |
| :--------------------------------------- |
| Valores negativos não devem ser aceitos. |

| **Resultado da execução**                                                                           |
| :-------------------------------------------------------------------------------------------------- |
| **Falhou.** O valor -5 foi salvo sem nenhum aviso. O campo foi restaurado para 120 logo em seguida. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Ocultação de senhas e tokens.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C25-CT06 | Verificar se os campos de senha e de token ficam mascarados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de configurações                                                              |
| **QUANDO** abrirmos as abas "Biometria", "Pagamento" e "Integrações"                                       |
| **ENTÃO** a "Senha" da biometria, o "Token Pagar.me" e o "ACCESS TOKEN" deverão aparecer mascarados (••••) |

| **Critérios de aceitação**                          |
| :-------------------------------------------------- |
| Credenciais não devem ser exibidas em texto aberto. |

| **Resultado da execução**                                                                                           |
| :------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O "ACCESS TOKEN" é mascarado, mas a "Senha" da biometria e o "Token Pagar.me" aparecem em texto aberto. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---
