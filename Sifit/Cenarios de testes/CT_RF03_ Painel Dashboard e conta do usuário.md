## Cenário 03: Painel Dashboard e conta do usuário.

### Caso de Teste 01: Abrir o painel Dashboard.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C03-CT01 | O item Dashboard abre uma tela diferente da página inicial. |

| **Pré-condições**                  |
| :--------------------------------- |
| A conta de teste está autenticada. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que estamos logados no Sifit                                             |
| **QUANDO** clicamos em Dashboard no menu PRINCIPAL                                |
| **ENTÃO** a rota muda para `/dash`                                                |
| **E** a tela mostra Despesas Fixas, Inteligência Sifit e o botão Ver Inteligência |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| O menu Dashboard não repete a página inicial. A rota fica `/dash`. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 02: Ver o usuário logado no topo.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C03-CT02 | O topo identifica o usuário Jair e o perfil Administrador. |

| **Pré-condições**                      |
| :------------------------------------- |
| Uma tela interna do Sifit está aberta. |

| **Passos**                                         |
| :------------------------------------------------- |
| **DADO** que estamos autenticados                  |
| **QUANDO** olhamos o canto do usuário              |
| **ENTÃO** o nome Jair aparece                      |
| **E** o perfil Administrador aparece junto do nome |

| **Critérios de aceitação**                                              |
| :---------------------------------------------------------------------- |
| Dá para saber quem está logado e qual é o perfil, sem abrir outra tela. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 03: Alternar o tema e voltar para o claro.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C03-CT03 | Os botões Claro e Escuro trocam o tema e permitem desfazer. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| Uma tela interna está aberta, com os botões Claro e Escuro visíveis. |

| **Passos**                                               |
| :------------------------------------------------------- |
| **DADO** que a tela mostra os botões Claro e Escuro      |
| **QUANDO** clicamos em Escuro                            |
| **ENTÃO** o tema da tela muda                            |
| **E** ao clicar em Claro o tema volta ao estado anterior |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A troca de tema é reversível e não altera dados da academia. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 04: Sair da conta pelo botão Sair.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C03-CT04 | O botão Sair encerra a sessão e volta para o login. |

| **Pré-condições**                                         |
| :-------------------------------------------------------- |
| Uma tela interna está aberta e o botão Sair está visível. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos autenticados                               |
| **QUANDO** clicamos em Sair                                     |
| **ENTÃO** a sessão é encerrada                                  |
| **E** a tela de login volta a ser exibida                       |
| **E** ao abrir `/dashboard` de novo o sistema pede autenticação |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| Depois de sair, a página inicial não abre sem um novo login. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---
