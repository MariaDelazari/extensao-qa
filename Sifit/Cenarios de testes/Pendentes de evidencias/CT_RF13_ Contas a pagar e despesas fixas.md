## Cenário 13: Contas a pagar e despesas fixas.

### Caso de Teste 01: Acesso à tela de contas a pagar.

| ID       | Descrição                                                                                    |
| :------- | :------------------------------------------------------------------------------------------- |
| C13-CT01 | Verificar se a tela de contas a pagar é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                           |
| :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                           |
| **QUANDO** acessarmos o menu "Contas a Pagar"                                                                                                        |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Total a Pagar, Valor Restante, Contas Listadas e Contas Atrasadas) e a listagem de contas |

| **Critérios de aceitação**                                                               |
| :--------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de contas a pagar com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 02: Busca de conta a pagar pelo fornecedor.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C13-CT02 | Verificar se a busca pelo nome do fornecedor retorna as contas correspondentes. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem contas do fornecedor pesquisado. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a pagar                                    |
| **E** informamos "centrion" no campo "Fornecedor ou colaborador"                  |
| **QUANDO** clicarmos no botão "Buscar"                                            |
| **ENTÃO** a listagem deverá exibir somente as contas do fornecedor "Centrion Web" |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O sistema deve filtrar as contas pelo fornecedor informado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 03: Filtro de contas a pagar por status.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C13-CT03 | Verificar se o filtro "Status" exibe somente as contas com o status selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a pagar                          |
| **E** selecionamos "Pendente" no filtro "Status"                        |
| **QUANDO** clicarmos no botão "Buscar"                                  |
| **ENTÃO** a listagem deverá exibir somente contas com status "PENDENTE" |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O sistema deve filtrar corretamente a listagem conforme o status selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 04: Indicadores de valores a pagar.

| ID       | Descrição                                                                                    |
| :------- | :------------------------------------------------------------------------------------------- |
| C13-CT04 | Verificar se os indicadores "Total a Pagar" e "Valor Restante" refletem as contas pendentes. |

| **Pré-condições**                                                                  |
| :--------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta pendente de R$ 200,00 no período. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que a listagem exibe uma conta pendente de R$ 200,00 no período        |
| **QUANDO** observarmos os indicadores "Total a Pagar" e "Valor Restante"        |
| **ENTÃO** os indicadores deverão exibir o valor das contas pendentes do período |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| Os indicadores devem somar os valores das contas listadas. |

| **Resultado da execução**            |
| :----------------------------------- |
| **Falhou.** Os indicadores exibem 0. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 05: Criar conta a pagar com campos vazios.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C13-CT05 | A conta a pagar não é salva com os campos vazios e o sistema orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Conta" em `/contas-pagar`                  |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em salvar                                         |
| **ENTÃO** o sistema informa quais campos faltam, sem erro de servidor |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução**                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A requisição `POST /api/cadastrar-conta-pagar/1` retornou 500 e a tela mostrou "Erro ao salvar conta a pagar". |

| **Evidência(s)**               |
| :----------------------------- |
| [PENDENTE VÍDEO] (roteiro V12) |

---

### Caso de Teste 06: Cadastro de conta a pagar com dados válidos.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C13-CT06 | Verificar se a conta a pagar é cadastrada ao informar os dados corretamente. |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado. |

| **Passos**                                                                                                                                         |
| :------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Nova Conta"                                                                                                         |
| **E** informamos o título "Teste Ville Nunes", o fornecedor "Centrion Web", o valor R$ 50,00, a categoria "Contas do dia a dia" e o local "Teste2" |
| **QUANDO** clicarmos no botão "Salvar"                                                                                                             |
| **ENTÃO** a conta deverá constar na listagem com status "PENDENTE"                                                                                 |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve cadastrar a conta e exibi-la na listagem. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 07: Visualização da conta a pagar.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C13-CT07 | Verificar se os dados da conta são exibidos de forma legível. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta a pagar cadastrada. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a pagar                                                                    |
| **QUANDO** clicarmos no botão "Visualizar" da conta "Teste Ville Nunes"                                           |
| **ENTÃO** deverão ser exibidos o código, o título, o tipo, a categoria pelo nome e as datas no formato dd/mm/aaaa |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| A visualização deve apresentar os dados completos e legíveis. |

| **Resultado da execução**                                                                      |
| :--------------------------------------------------------------------------------------------- |
| **Falhou.** São exibidos códigos internos, campo de código vazio e data no formato aaaa-mm-dd. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 08: Registro do pagamento da conta.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C13-CT08 | Verificar se é possível registrar o pagamento de uma conta pendente. |

| **Pré-condições**                                          |
| :--------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta pendente. |

| **Passos**                                                                               |
| :--------------------------------------------------------------------------------------- |
| **DADO** que existe a conta pendente "Teste Ville Nunes"                                 |
| **QUANDO** procurarmos na listagem e na visualização a opção de efetuar o pagamento      |
| **ENTÃO** o sistema deverá permitir registrar o pagamento e alterar o status para "PAGO" |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve permitir registrar o pagamento das contas a pagar. |

| **Resultado da execução**                                    |
| :----------------------------------------------------------- |
| **Falhou.** Não há nenhuma opção para registrar o pagamento. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 09: Exclusão de conta a pagar.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C13-CT09 | Verificar se a conta é excluída ao confirmar a exclusão. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta de teste cadastrada. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a pagar                                                      |
| **E** clicamos no botão "Deletar" da conta "Teste Ville Nunes"                                      |
| **QUANDO** confirmarmos a mensagem "Deseja deletar esta conta?"                                     |
| **ENTÃO** a conta não deverá mais constar na listagem e nenhuma mensagem de erro deverá ser exibida |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O sistema deve excluir a conta sem exibir erro. |

| **Resultado da execução**                                               |
| :---------------------------------------------------------------------- |
| **Falhou.** A conta é excluída, mas o sistema exibe "Erro no servidor". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 10: Acesso à tela de despesas fixas.

| ID       | Descrição                                                                                    |
| :------- | :------------------------------------------------------------------------------------------- |
| C13-CT10 | Verificar se a tela de despesas fixas é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos autenticados no SIFIT                                                                                      |
| **QUANDO** acessarmos o menu "Despesas Fixas"                                                                                   |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Despesas, Ativas, Inativas e Valor Listado) e a listagem de despesas |

| **Critérios de aceitação**                                                               |
| :--------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de despesas fixas com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 11: Filtro de despesas fixas por recorrência.

| ID       | Descrição                                                                                    |
| :------- | :------------------------------------------------------------------------------------------- |
| C13-CT11 | Verificar se o filtro "Recorrência" exibe somente as despesas com a recorrência selecionada. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                   |
| :--------------------------------------------------------------------------- |
| **DADO** que estamos na tela de despesas fixas                               |
| **E** selecionamos "1 Mês" no filtro "Recorrência"                           |
| **QUANDO** clicarmos no botão "Buscar"                                       |
| **ENTÃO** a listagem deverá exibir somente despesas com recorrência de 1 mês |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve filtrar as despesas pela recorrência selecionada. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 12: Cadastro de despesa fixa com campos vazios.

| ID       | Descrição                                                             |
| :------- | :-------------------------------------------------------------------- |
| C13-CT12 | Verificar se o sistema impede o cadastro de despesa sem nome e valor. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                               |
| :--------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Nova Despesa"                                             |
| **E** mantemos os campos "Nome" e "Valor" vazios                                         |
| **QUANDO** clicarmos no botão "Salvar Despesa"                                           |
| **ENTÃO** o sistema deverá solicitar o preenchimento dos campos ("Preencha este campo.") |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que nome e valor sejam informados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 13: Cadastro de despesa fixa com valor negativo.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C13-CT13 | Verificar se o sistema impede o cadastro de despesa com valor negativo. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Nova Despesa"                            |
| **E** informamos o nome "Despesa Teste Ville Negativa" e o valor "-100" |
| **QUANDO** clicarmos no botão "Salvar Despesa"                          |
| **ENTÃO** o sistema deverá informar que o valor deve ser maior que zero |

| **Critérios de aceitação**                        |
| :------------------------------------------------ |
| O sistema deve aceitar somente valores positivos. |

| **Resultado da execução**                              |
| :----------------------------------------------------- |
| **Falhou.** A despesa é cadastrada com valor negativo. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 14: Cadastro de despesa fixa com dados válidos.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C13-CT14 | Verificar se a despesa fixa é cadastrada e os indicadores são atualizados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Nova Despesa"                                                               |
| **E** informamos o nome "Despesa Teste Ville", um valor e a recorrência "1 Mês"                            |
| **QUANDO** clicarmos no botão "Salvar Despesa"                                                             |
| **ENTÃO** a despesa deverá constar na listagem com status "ATIVO" e os indicadores deverão ser atualizados |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema deve cadastrar a despesa e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 15: Alteração e inativação de despesa fixa.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C13-CT15 | Verificar se as alterações e a inativação da despesa são salvas. |

| **Pré-condições**                                                           |
| :-------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a despesa "Despesa Teste Ville". |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Visualizar" da despesa "Despesa Teste Ville"                |
| **E** alteramos o nome para "Despesa Teste Ville Editada" e o valor para 89,90        |
| **E** salvamos e depois alteramos o status para "Inativo"                             |
| **QUANDO** clicarmos no botão "Salvar Despesa"                                        |
| **ENTÃO** a listagem deverá exibir o nome e o valor atualizados, com status "INATIVO" |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema deve salvar as alterações e a inativação da despesa. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 16: Exclusão de despesa fixa.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C13-CT16 | Verificar se a despesa é excluída ao confirmar a exclusão. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir despesa de teste cadastrada. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que estamos na tela de despesas fixas                             |
| **E** clicamos no botão "Deletar" da despesa "Despesa Teste Ville Editada" |
| **QUANDO** confirmarmos a mensagem "Deseja deletar a despesa fixa?"        |
| **ENTÃO** a despesa não deverá mais constar na listagem                    |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve solicitar confirmação e excluir a despesa. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |
