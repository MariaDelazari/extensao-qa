## Cenário 12: Caixas.

### Caso de Teste 01: Acesso à tela de caixas.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C12-CT01 | Verificar se a tela de caixas é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                           |
| :------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                           |
| **QUANDO** acessarmos o menu "Caixas"                                                                                |
| **ENTÃO** a tela deverá exibir os filtros (Data Inicial, Data Final e Status), os indicadores e a listagem de caixas |

| **Critérios de aceitação**                                                       |
| :------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de caixas com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/f0c5a138-6479-449c-86fa-384bcea27ad5) |

---

### Caso de Teste 02: Listagem inicial conforme o período exibido.

| ID       | Descrição                                                                                  |
| :------- | :----------------------------------------------------------------------------------------- |
| C12-CT02 | Verificar se a listagem exibida ao abrir a tela respeita o período preenchido nos filtros. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela de caixas                                                                                                |
| **E** o filtro exibe o período de 01/11/2026 a 31/11/2026                                                                              |
| **QUANDO** a listagem for carregada                                                                                                    |
| **ENTÃO** deverão ser exibidos somente os caixas do período e o indicador "Registros no Periodo" deverá corresponder a essa quantidade |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| A listagem inicial deve respeitar o período exibido nos filtros. |

| **Resultado da execução**                                              |
| :--------------------------------------------------------------------- |
| **Falhou.** A listagem inicial exibe todos os caixas, fora do período. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Busca de caixas por período.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C12-CT03 | Verificar se a busca retorna somente os caixas do período informado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de caixas com o período de 01/10/2026 a 31/10/2026 |
| **QUANDO** clicarmos no botão "Buscar"                                          |
| **ENTÃO** a listagem deverá exibir somente os caixas abertos no período         |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve filtrar os caixas pelo período informado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Filtro de caixas por status.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C12-CT04 | Verificar se o filtro "Status" exibe somente os caixas com o status selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de caixas                                |
| **E** selecionamos "Aberto" no filtro "Status"                        |
| **QUANDO** clicarmos no botão "Buscar"                                |
| **ENTÃO** a listagem deverá exibir somente caixas com status "ABERTO" |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O sistema deve filtrar corretamente a listagem conforme o status selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Paginação da listagem de caixas.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C12-CT05 | Verificar se a paginação e a quantidade por página funcionam. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de caixas com 20 registros                                                           |
| **QUANDO** clicarmos na página "2" e depois selecionarmos "20 por pagina"                                         |
| **ENTÃO** a página 2 deverá exibir os registros seguintes e a opção "20 por pagina" deverá exibir os 20 registros |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| A paginação deve permitir acessar todos os caixas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Abrir caixa com campos vazios.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C12-CT06 | O caixa não é aberto com campos vazios e o sistema orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                    |
| :------------------------------------------------------------ |
| **DADO** que abrimos "Abrir Caixa" em `/caixas`               |
| **E** deixamos os campos sem preencher                        |
| **QUANDO** clicamos para confirmar a abertura                 |
| **ENTÃO** o sistema informa o que falta, sem erro de servidor |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução**                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao abrir o caixa sem preencher nada, a tela mostrou "Erro no servidor. Erro interno inesperado." e não indicou o que falta. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Abertura de caixa com dados válidos.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C12-CT07 | Verificar se o caixa é aberto para o local selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                       |
| :--------------------------------------------------------------- |
| **DADO** que abrimos a janela "Abrir Caixa"                      |
| **E** selecionamos o local "Teste2" e a data atual               |
| **QUANDO** clicarmos no botão "Salvar"                           |
| **ENTÃO** o caixa deverá constar na listagem com status "ABERTO" |

| **Critérios de aceitação**                           |
| :--------------------------------------------------- |
| O sistema deve abrir o caixa e exibi-lo na listagem. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Abertura de caixa duplicado no mesmo local.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C12-CT08 | Verificar se o sistema impede abrir mais de um caixa no mesmo local. |

| **Pré-condições**                                                          |
| :------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir caixa aberto no local "Teste2". |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que existe um caixa aberto no local "Teste2"                          |
| **E** abrimos a janela "Abrir Caixa" e selecionamos o local "Teste2"           |
| **QUANDO** clicarmos no botão "Salvar"                                         |
| **ENTÃO** o sistema deverá informar que já existe um caixa aberto para o local |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O sistema deve permitir somente um caixa aberto por local. |

| **Resultado da execução**                             |
| :---------------------------------------------------- |
| **Falhou.** Um segundo caixa é aberto no mesmo local. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Indicadores de caixas abertos e fechados.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C12-CT09 | Verificar se os indicadores são atualizados corretamente ao abrir e fechar caixas. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| **DADO** que os indicadores exibem 3 caixas abertos e 17 fechados                                                   |
| **QUANDO** abrirmos um novo caixa                                                                                   |
| **ENTÃO** o indicador "Caixas Abertos" deverá passar para 4 e o indicador "Caixas Fechados" deverá permanecer em 17 |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| Os indicadores devem refletir a quantidade real de caixas abertos e fechados. |

| **Resultado da execução**                                       |
| :-------------------------------------------------------------- |
| **Falhou.** "Caixas Fechados" diminui em 1 a cada caixa aberto. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Fechamento de caixa com conferência das contas.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C12-CT10 | Verificar se o caixa é fechado após buscar e conferir as contas do período. |

| **Pré-condições**                                        |
| :------------------------------------------------------- |
| O usuário deve estar autenticado e existir caixa aberto. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Visualizar" de um caixa aberto                        |
| **E** selecionamos o local de contas e clicamos em "Buscar Contas"              |
| **QUANDO** clicarmos no botão "Salvar"                                          |
| **ENTÃO** o caixa deverá constar com status "FECHADO" e a data final preenchida |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema deve fechar o caixa com os totais conferidos. |

| **Resultado da execução**                             |
| :---------------------------------------------------- |
| **Falhou.** Nada acontece e o caixa permanece aberto. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Fechamento de caixa sem buscar as contas.

| ID       | Descrição                                                                         |
| :------- | :-------------------------------------------------------------------------------- |
| C12-CT11 | Verificar se o sistema impede o fechamento do caixa sem a conferência das contas. |

| **Pré-condições**                                        |
| :------------------------------------------------------- |
| O usuário deve estar autenticado e existir caixa aberto. |

| **Passos**                                                                                  |
| :------------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Visualizar" de um caixa aberto                                    |
| **E** não clicamos em "Buscar Contas"                                                       |
| **QUANDO** clicarmos no botão "Salvar"                                                      |
| **ENTÃO** o sistema deverá solicitar a busca e a conferência das contas antes do fechamento |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema não deve fechar o caixa sem a conferência dos totais. |

| **Resultado da execução**                            |
| :--------------------------------------------------- |
| **Falhou.** O caixa é fechado com os totais zerados. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
