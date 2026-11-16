## Cenário 32: Métricas do cliente na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Métricas de Clientes pelo menu.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C32-CT01 | Verificar se a tela Métricas de Clientes aparece no menu. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                    |
| :------------------------------------------------------------ |
| **DADO** que estamos autenticados no SIFIT                    |
| **QUANDO** procurarmos "Métricas de Clientes" no menu lateral |
| **ENTÃO** deverá existir um item para a tela                  |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| O sistema deve oferecer acesso à tela Métricas de Clientes pelo menu. |

| **Resultado da execução**                                                                                |
| :------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. A tela só abre pelo link (/metricas-cliente) e abre sem o menu lateral. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Exibição das métricas do período.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C32-CT02 | Verificar se a tela exibe as métricas dos clientes no período informado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente |
| **E** o período é 01/11/2026 a 30/11/2026                                                                       |
| **QUANDO** clicarmos em "Buscar"                                                                                |
| **ENTÃO** deverão aparecer as métricas dos clientes do período, como o gráfico de gênero                        |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O sistema deve exibir as métricas dos clientes do período. |

| **Resultado da execução**                                                                                                                                                                                                     |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Nada aparece na tela: "Gênero" fica sem gráfico. A API (POST /api/dados-principais-home/1) devolve os números do período (14 clientes ativos, 4 matrículas, 10 sem matrícula e 2 personais), sem dados de gênero. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Listas de Clientes Ausentes, Sem Matrículas e Personais.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C32-CT03 | Verificar se as listas de clientes são exibidas com os dados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                           |
| :------------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente      |
| **QUANDO** clicarmos em "Buscar"                                                                                     |
| **ENTÃO** as listas Clientes Ausentes, Clientes Sem Matrículas e Personais deverão mostrar os clientes de cada grupo |

| **Critérios de aceitação**                       |
| :----------------------------------------------- |
| O sistema deve listar os clientes de cada grupo. |

| **Resultado da execução**                                                                                                                                 |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** As três listas aparecem abertas na página, como janelas soltas, e ficam vazias, embora a API informe 10 clientes sem matrícula e 2 personais. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Botão "Fechar" das listas.

| ID       | Descrição                                    |
| :------- | :------------------------------------------- |
| C32-CT04 | Verificar se o botão "Fechar" fecha a lista. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente |
| **QUANDO** clicarmos em "Fechar" abaixo de "Clientes Ausentes"                                                  |
| **ENTÃO** a lista deverá ser fechada                                                                            |

| **Critérios de aceitação**                           |
| :--------------------------------------------------- |
| O sistema deve fechar a lista ao clicar em "Fechar". |

| **Resultado da execução**                              |
| :----------------------------------------------------- |
| **Falhou.** Nada acontece. A lista continua na página. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Período com data inicial maior que a final.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C32-CT05 | Verificar se o sistema impede a busca com a data inicial depois da data final. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente |
| **E** escolhemos no calendário a data inicial 30/11/2026 e a data final 01/11/2026                              |
| **QUANDO** clicarmos em "Buscar"                                                                                |
| **ENTÃO** o sistema deverá avisar que o período é inválido e não buscar                                         |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| O sistema deve recusar período com a data inicial maior que a final. |

| **Resultado da execução**                                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Nenhum aviso aparece. A busca é enviada com o período invertido (30/11/2026 a 01/11/2026) e a API responde normalmente. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Escolha do período pelo calendário.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C32-CT06 | Verificar se as datas escolhidas no calendário são usadas na busca. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Métricas de Clientes pelo link https://sifitalfa.centrion.com.br/metricas-cliente |
| **QUANDO** escolhermos no calendário a data inicial e a data final                                              |
| **ENTÃO** as datas escolhidas deverão aparecer nos campos e ser usadas ao clicar em "Buscar"                    |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve usar na busca o período escolhido no calendário. |

| **Resultado da execução**                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------- |
| **Passou.** As datas escolhidas aparecem nos campos "Data Inicial" e "Data final" e a busca é enviada com esse período. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
