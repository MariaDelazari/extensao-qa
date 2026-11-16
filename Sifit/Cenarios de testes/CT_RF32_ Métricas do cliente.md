## Cenário 32: Métricas do cliente na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Métricas de Clientes pelo menu.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C32-CT01 | Verificar se a tela Métricas de Clientes aparece no menu. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                           |
| **QUANDO** procurarmos "Métricas de Clientes" no menu lateral                        |
| **E** acessarmos a tela pelo link https://sifitalfa.centrion.com.br/metricas-cliente |
| **ENTÃO** a tela deverá ter item no menu e abrir com o menu lateral                  |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| O sistema deve oferecer acesso à tela Métricas de Clientes pelo menu. |

| **Resultado da execução**                                                                                |
| :------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. A tela só abre pelo link (/metricas-cliente) e abre sem o menu lateral. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/21553d8f-7a1a-45a5-a29f-df1c3369ac5d) |

---

### Caso de Teste 02: Busca das métricas do período.

| ID       | Descrição                                                                           |
| :------- | :---------------------------------------------------------------------------------- |
| C32-CT02 | Verificar se a tela exibe as métricas e as listas de clientes do período escolhido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente                              |
| **E** escolhemos no calendário o período de 01/11/2026 a 27/11/2026                                                                          |
| **QUANDO** clicarmos em "Buscar"                                                                                                             |
| **E** clicarmos em "Fechar" abaixo das listas                                                                                                |
| **ENTÃO** deverão aparecer as métricas do período (como o gráfico de gênero) e os clientes de cada lista, e o "Fechar" deverá fechar a lista |

| **Critérios de aceitação**                                                                                   |
| :----------------------------------------------------------------------------------------------------------- |
| O sistema deve exibir as métricas e as listas de clientes do período e fechar a lista ao clicar em "Fechar". |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                            |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A busca é enviada com o período escolhido e a API (POST /api/dados-principais-home/1) devolve 14 clientes ativos, 4 matrículas, 10 sem matrícula e 2 personais, mas nada aparece na tela: "Gênero" fica sem gráfico, as listas Clientes Ausentes, Clientes Sem Matrículas e Personais ficam abertas e vazias, e o "Fechar" não faz nada. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/25449cc3-2e0f-4c99-a48d-bfe50ccf32df) |
