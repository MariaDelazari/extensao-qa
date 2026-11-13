## Cenário 07: Contas a receber.

### Caso de Teste 01: Acesso à tela de contas a receber.

| ID       | Descrição                                                                                             |
| :------- | :---------------------------------------------------------------------------------------------------- |
| C07-CT01 | Verificar se a tela de contas a receber é exibida com os filtros, os indicadores e a listagem do mês. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                                                |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                |
| **QUANDO** acessarmos o menu "Contas a Receber"                                                                                                                                           |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Entradas, Saídas, Líquido, Previsto para o Mês, Recebido no Mês, Pendentes no Mês e Contas Atrasadas) e as contas do mês atual |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O sistema deve exibir a tela com indicadores coerentes com as contas listadas. |

| **Resultado da execução**                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: lista todas as contas do período. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/86b8664e-46a9-4911-aa48-8f5b3c65cac5) |

---

### Caso de Teste 02: Busca de conta pelo nome do cliente.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C07-CT02 | Verificar se a busca pelo nome do cliente retorna as contas correspondentes. |

| **Pré-condições**                                                                      |
| :------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta cadastrada para o cliente pesquisado. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a receber                            |
| **E** informamos "Steven Kaiki" no campo "Nome do cliente"                  |
| **QUANDO** clicarmos no botão "Buscar"                                      |
| **ENTÃO** a listagem deverá exibir apenas as contas do cliente Steven Kaiki |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar as contas pelo nome do cliente, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7501b236-4a18-4e5b-8b7b-19a9866252b2) |

---

### Caso de Teste 03: Busca de conta com nome inexistente.

| ID       | Descrição                                                                                         |
| :------- | :------------------------------------------------------------------------------------------------ |
| C07-CT03 | Verificar se o sistema informa que nenhuma conta foi encontrada ao pesquisar um nome inexistente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a receber                                               |
| **E** informamos um nome inexistente no campo "Nome do cliente"                                |
| **QUANDO** clicarmos no botão "Buscar"                                                         |
| **ENTÃO** o sistema deverá apresentar uma mensagem informando que nenhuma conta foi encontrada |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa em vez de apenas uma tabela vazia. |

| **Resultado da execução**                                                                |
| :--------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/22ec822a-9cc2-412b-b1dd-3354f81136a8) |

---

### Caso de Teste 04: Filtro de contas por status.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C07-CT04 | Verificar se o filtro "Status" exibe somente as contas com o status selecionado. |

| **Pré-condições**                                                          |
| :------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem contas pendentes e recebidas. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a receber                        |
| **E** selecionamos "Pendente" no filtro "Status"                        |
| **QUANDO** clicarmos no botão "Buscar"                                  |
| **ENTÃO** a listagem deverá exibir somente contas com status "PENDENTE" |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O sistema deve filtrar corretamente a listagem conforme o status selecionado. |

| **Resultado da execução**                                                                                                                                                          |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: lista traz as contas pendentes do período. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/62e46604-54da-4df0-b860-312f55b5cc6f) |

---

### Caso de Teste 05: Consistência do indicador de contas atrasadas.

| ID       | Descrição                                                                                                     |
| :------- | :------------------------------------------------------------------------------------------------------------ |
| C07-CT05 | Verificar se a quantidade do indicador "Contas Atrasadas" corresponde às contas exibidas no filtro "Vencido". |

| **Pré-condições**                                                                                   |
| :-------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e o indicador "Contas Atrasadas" deve exibir valor maior que zero. |

| **Passos**                                                                                |
| :---------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a receber e o indicador "Contas Atrasadas" exibe 2 |
| **E** selecionamos "Vencido" no filtro "Status"                                           |
| **QUANDO** clicarmos no botão "Buscar"                                                    |
| **ENTÃO** a listagem deverá exibir as 2 contas atrasadas                                  |

| **Critérios de aceitação**                                                           |
| :----------------------------------------------------------------------------------- |
| O indicador e o filtro de contas vencidas devem apresentar informações consistentes. |

| **Resultado da execução**                       |
| :---------------------------------------------- |
| **Falhou.** A listagem não exibe nenhuma conta. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e32d62f2-82da-4f71-b65d-8c9ebfff90c1) |

---

### Caso de Teste 06: Cadastro de conta com campos obrigatórios vazios.

| ID       | Descrição                                                                              |
| :------- | :------------------------------------------------------------------------------------- |
| C07-CT06 | Verificar se o sistema impede o cadastro da conta quando nenhum cliente é selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Nova Conta"                          |
| **E** mantemos os campos vazios                                         |
| **QUANDO** clicarmos no botão "Salvar"                                  |
| **ENTÃO** o sistema deverá apresentar a mensagem "Selecione o cliente." |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o cliente seja selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/53df6e00-d993-429c-9c5d-cbe0dcd020fc) |

---

### Caso de Teste 07: Cadastro de conta com dados válidos.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C07-CT07 | Verificar se a conta é cadastrada e os indicadores são atualizados. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                                                                         |
| :--------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Nova Conta"                                                                                     |
| **E** selecionamos a cliente "Lila", o status "Pendente", o título "Teste Ville Nunes" e o valor R$ 75,50                          |
| **QUANDO** clicarmos no botão "Salvar"                                                                                             |
| **ENTÃO** a conta deverá constar na listagem com status "PENDENTE" e o indicador "Previsto para o Mês" deverá aumentar em R$ 75,50 |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve cadastrar a conta e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/6d081933-b9ae-48f0-9891-dbda95715493) |

---

### Caso de Teste 08: Recebimento de conta pendente.

| ID       | Descrição                                                                           |
| :------- | :---------------------------------------------------------------------------------- |
| C07-CT08 | Verificar se a baixa (recebimento) de uma conta pendente é registrada corretamente. |

| **Pré-condições**                                                           |
| :-------------------------------------------------------------------------- |
| O usuário deve estar autenticado, existir conta pendente e um caixa aberto. |

| **Passos**                                                                                            |
| :---------------------------------------------------------------------------------------------------- |
| **DADO** que estamos visualizando uma conta pendente                                                  |
| **E** clicamos em "Efetuar Recebimento"                                                               |
| **QUANDO** clicarmos em "Salvar" e confirmarmos a mensagem do caixa                                   |
| **ENTÃO** a conta deverá constar com status "RECEBIDO" e o indicador "Entradas" deverá ser atualizado |

| **Critérios de aceitação**                                                                     |
| :--------------------------------------------------------------------------------------------- |
| O sistema deve registrar o recebimento, atualizar o status da conta e o indicador de entradas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/cfa8bb62-df28-401b-ad95-8918fca5b4b4) |

---

### Caso de Teste 09: Recebimento de conta sem tipo de pagamento.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C07-CT09 | Verificar se o sistema impede o recebimento quando o tipo de pagamento não é selecionado. |

| **Pré-condições**                                                           |
| :-------------------------------------------------------------------------- |
| O usuário deve estar autenticado, existir conta pendente e um caixa aberto. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que estamos na tela "Efetuar Recebimento" de uma conta pendente  |
| **E** não selecionamos o tipo de pagamento                                |
| **QUANDO** clicarmos em "Salvar"                                          |
| **ENTÃO** o sistema deverá informar que o tipo de pagamento é obrigatório |

| **Critérios de aceitação**                                                         |
| :--------------------------------------------------------------------------------- |
| O sistema deve impedir o recebimento até que o tipo de pagamento seja selecionado. |

| **Resultado da execução**                                             |
| :-------------------------------------------------------------------- |
| **Falhou.** O recebimento é registrado com o tipo de pagamento vazio. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/46be9dfa-3e49-40c1-a8f7-0771f9f8a67e) |

---

### Caso de Teste 10: Recebimento com valor maior que o valor a receber.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C07-CT10 | Verificar se o sistema alerta quando o valor recebido é maior que o valor a receber. |

| **Pré-condições**                                                           |
| :-------------------------------------------------------------------------- |
| O usuário deve estar autenticado, existir conta pendente e um caixa aberto. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela "Efetuar Recebimento" de uma conta de R$ 75,50           |
| **E** informamos o valor recebido de R$ 100,00                                        |
| **QUANDO** clicarmos em "Salvar"                                                      |
| **ENTÃO** o sistema deverá alertar que o valor recebido é maior que o valor a receber |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| O sistema deve impedir ou alertar o recebimento com valor divergente. |

| **Resultado da execução**                                               |
| :---------------------------------------------------------------------- |
| **Falhou.** O recebimento é registrado com R$ 100,00 sem nenhum alerta. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f28fd023-7766-4e7e-87eb-419aad2d2797) |

---

### Caso de Teste 11: Exclusão de conta a receber.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C07-CT11 | Verificar se a conta é excluída ao confirmar a exclusão. |

| **Pré-condições**                                            |
| :----------------------------------------------------------- |
| O usuário deve estar autenticado e existir conta cadastrada. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de contas a receber                                               |
| **E** clicamos no botão "Deletar" de uma conta                                                 |
| **QUANDO** confirmarmos a mensagem "Deseja deletar esta conta?"                                |
| **ENTÃO** a conta não deverá mais constar na listagem e os indicadores deverão ser atualizados |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema deve solicitar confirmação, excluir a conta e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7ab623ac-252c-412c-96bd-49f9db808190) |

---

### Caso de Teste 12: Geração de conta a receber a partir da matrícula.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C07-CT12 | Verificar se o cadastro de uma matrícula gera a conta a receber correspondente. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente sem matrícula ativa. |

| **Passos**                                                                                                                                     |
| :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que cadastramos uma matrícula, confirmamos as parcelas em "Escolher" e salvamos a tela "Cadastrar Conta a Receber" exibida em seguida |
| **QUANDO** acessarmos a tela de contas a receber e pesquisarmos o cliente em um período amplo                                                  |
| **ENTÃO** deverá existir a conta a receber da primeira parcela da matrícula, com o valor do plano                                              |

| **Critérios de aceitação**                                                          |
| :---------------------------------------------------------------------------------- |
| O sistema deve gerar automaticamente as contas a receber das parcelas da matrícula. |

| **Resultado da execução**                                                                                                                                                                       |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: parcela listada com o valor do plano e status PENDENTE. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/68fb4963-d268-4a72-bd29-45e807c138d0) |

---

### Caso de Teste 13: Conferir os totais com a listagem.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C07-CT13 | Os totais do topo de Contas a Receber batem com as linhas da listagem. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/contas-receber` com o período do mês                                                    |
| **QUANDO** somamos as linhas da listagem                                                                          |
| **ENTÃO** "Entradas", "Previsto para o Mês" e "Recebido no Mês" estão de acordo com os valores recebidos da lista |
| **E** nenhuma linha tem valor recebido maior que o valor a receber sem explicação                                 |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| Os totais e os valores recebidos da listagem são coerentes entre si. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                         |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** Os cards "Pendentes no Mês" e "Previsto para o Mês" não refletem as contas pendentes do mês filtrado. Em 28/10/2026, no Sifit Unialfa, o caso falhou: as linhas somam R$ 499,50 (igual a "Entradas"), mas "Recebido no Mês" mostra R$ 475,00 com "100,00% recebido". A conta 1608 (Lila) tem R$ 75,50 a receber e R$ 100,00 recebido. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/d2060185-943a-429b-bb7f-786c1bcd6119) |
