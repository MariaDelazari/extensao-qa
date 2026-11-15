## Cenário 06: Gestão de matrículas.

### Caso de Teste 01: Abrir a listagem de matrículas.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C06-CT01 | A tela de matrículas mostra os indicadores e a listagem. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                 |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados                                                                                                                          |
| **QUANDO** clicamos em "Matrículas" no menu lateral                                                                                                        |
| **ENTÃO** a tela mostra os indicadores (Matrículas Ativas, Recorrentes, Não Renovadas, Cadastradas este Mês) e a listagem com código, nome, plano e status |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| A tela de matrículas abre com indicadores e listagem preenchidos. |

| **Resultado da execução**                                                                                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso passou: a tela abriu com os indicadores (3 ativas, 0 recorrentes, 60 não renovadas, 3 cadastradas no mês) e a listagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/695d94cf-df81-4c1c-9015-eddaf5e13fbb) |

---

### Caso de Teste 02: Busca de matrícula pelo nome do cliente.

| ID       | Descrição                                                                                    |
| :------- | :------------------------------------------------------------------------------------------- |
| C06-CT02 | Verificar se a busca pelo nome retorna as matrículas do cliente, inclusive com nome parcial. |

| **Pré-condições**                                                                          |
| :----------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir matrícula cadastrada para o cliente pesquisado. |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que estamos na tela de matrículas                                    |
| **E** informamos o nome completo ou parte do nome do cliente no campo "Nome"  |
| **QUANDO** clicarmos no botão "Buscar"                                        |
| **ENTÃO** a listagem deverá exibir apenas as matrículas do cliente pesquisado |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar a listagem pelo nome informado, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/9ad7db75-32ff-4044-be36-b0ddd707e853) |

---

### Caso de Teste 03: Busca de matrícula com nome inexistente.

| ID       | Descrição                                                                                             |
| :------- | :---------------------------------------------------------------------------------------------------- |
| C06-CT03 | Verificar se o sistema informa que nenhuma matrícula foi encontrada ao pesquisar um nome inexistente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                         |
| :------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de matrículas                                                         |
| **E** informamos no campo "Nome" um nome que não possui matrícula                                  |
| **QUANDO** clicarmos no botão "Buscar"                                                             |
| **ENTÃO** o sistema deverá apresentar uma mensagem informando que nenhuma matrícula foi encontrada |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa em vez de apenas uma tabela vazia. |

| **Resultado da execução**                                                                |
| :--------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/d1626ff1-a6d5-43c0-a063-d9127141bb66) |

---

### Caso de Teste 04: Paginação da listagem de matrículas.

| ID       | Descrição                                                                              |
| :------- | :------------------------------------------------------------------------------------- |
| C06-CT04 | Verificar se é possível acessar todas as matrículas cadastradas por meio da paginação. |

| **Pré-condições**                                                               |
| :------------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existirem mais de 50 matrículas cadastradas. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de matrículas com a opção "50" registros por página |
| **QUANDO** observarmos a paginação e clicarmos no botão "Próxima"                |
| **ENTÃO** deveremos ser direcionados à página 2 com as demais matrículas         |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A paginação deve permitir acessar todas as matrículas cadastradas. |

| **Resultado da execução**                                                               |
| :-------------------------------------------------------------------------------------- |
| **Falhou.** A paginação exibe somente a página 1 e o botão "Próxima" fica desabilitado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/de75bafc-86f6-45f1-9e87-83269324988b) |

---

### Caso de Teste 05: Cadastrar matrícula sem escolher o cliente.

| ID       | Descrição                            |
| :------- | :----------------------------------- |
| C06-CT05 | A matrícula não é salva sem cliente. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                             |
| :--------------------------------------------------------------------- |
| **DADO** que estamos em "Cadastrar Matrícula" (`/adicionar-matricula`) |
| **E** não escolhemos o cliente                                         |
| **QUANDO** clicamos em "Salvar"                                        |
| **ENTÃO** o sistema avisa que o cliente precisa ser selecionado        |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema bloqueia o salvamento e mostra aviso sobre o cliente. |

| **Resultado da execução**                                                                                                                                                                                                                                                                           |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso passou: apareceu o aviso "Selecione o cliente!" e o cadastro não foi salvo. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: exibido o aviso "Selecione o cliente!". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/81fc31ca-5db8-4034-b846-06afff7026b2) |

---

### Caso de Teste 06: Cadastro de matrícula sem tipo de pagamento.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C06-CT06 | Verificar se o sistema impede o cadastro da matrícula quando o tipo de pagamento não é selecionado. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Cadastrar Matrícula"                               |
| **E** selecionamos um cliente e uma modalidade                                   |
| **E** não selecionamos o tipo de pagamento                                       |
| **QUANDO** clicarmos no botão "Salvar"                                           |
| **ENTÃO** o sistema deverá apresentar a mensagem "Selecione o Tipo de Pagamento" |

| **Critérios de aceitação**                                                      |
| :------------------------------------------------------------------------------ |
| O sistema deve impedir o cadastro até que o tipo de pagamento seja selecionado. |

| **Resultado da execução**                                                 |
| :------------------------------------------------------------------------ |
| **Falhou.** A mensagem "Selecione o Tipo de Pagamento" permanece exibida. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/5a82af04-828e-49bb-9853-4e01baa8aa28) |

---

### Caso de Teste 07: Cadastro de matrícula com dados válidos.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C06-CT07 | Verificar se a matrícula é cadastrada ao informar todos os dados corretamente. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente sem matrícula ativa. |

| **Passos**                                                                                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela "Cadastrar Matrícula"                                                                                                                              |
| **E** selecionamos o cliente, a modalidade e o tipo de pagamento                                                                                                                |
| **E** informamos o dia de vencimento (somente o dia, ex.: 10)                                                                                                                   |
| **QUANDO** clicarmos no botão "Salvar", confirmarmos a quantidade de parcelas em "Escolher" e confirmarmos a mensagem "Matrícula salva! Deseja pagar a primeira parcela agora?" |
| **ENTÃO** o sistema deverá exibir as parcelas da matrícula e a conta a receber da primeira parcela deverá constar em "Contas a Receber"                                         |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O sistema deve cadastrar a matrícula e gerar as contas a receber das parcelas. |

| **Resultado da execução**                                                                                                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Não foi possível concluir" com uma mensagem de erro do banco de dados. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: matrícula ATIVA; conta gerada (ver C07-CT01). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3e0d437f-4751-4ac1-b5d0-a2441e8de6de) |

---

### Caso de Teste 08: Cadastro de matrícula com desconto.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C06-CT08 | Verificar se o desconto informado é aplicado ao valor total da matrícula. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente sem matrícula ativa. |

| **Passos**                                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Cadastrar Matrícula" com cliente e modalidade "Treino Livre" (R$ 52,00) selecionados |
| **E** informamos o valor "10" no campo "Desconto"                                                                  |
| **QUANDO** clicarmos no botão "Salvar"                                                                             |
| **ENTÃO** o valor total deverá ser R$ 42,00 e a matrícula deverá exibir desconto de R$ 10,00                       |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| O sistema deve aplicar o desconto e calcular corretamente o valor total. |

| **Resultado da execução**                                                             |
| :------------------------------------------------------------------------------------ |
| **Falhou.** O valor total permanece R$ 52,00 e a visualização exibe "Desconto 52,00". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/561a6194-6092-4ce0-a67f-71e0da5a84ca) |

---

### Caso de Teste 09: Cadastro de matrícula para cliente com matrícula ativa.

| ID       | Descrição                                                                                                         |
| :------- | :---------------------------------------------------------------------------------------------------------------- |
| C06-CT09 | Verificar se o sistema impede uma nova matrícula para cliente que já possui matrícula ativa, informando o motivo. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente com matrícula ativa. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Cadastrar Matrícula"                          |
| **E** selecionamos um cliente que já possui matrícula ativa                 |
| **E** preenchemos os demais campos corretamente                             |
| **QUANDO** clicarmos no botão "Salvar"                                      |
| **ENTÃO** o sistema deverá informar que o cliente já possui matrícula ativa |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve impedir a matrícula duplicada e exibir uma mensagem clara com o motivo. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe a mensagem "Erro ao Cadastrar com Assinatura". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7058b67e-1662-4ab3-9b6c-5bdb8f2c041c) |

---

### Caso de Teste 10: Visualização dos dados da matrícula.

| ID       | Descrição                                                                               |
| :------- | :-------------------------------------------------------------------------------------- |
| C06-CT10 | Verificar se os dados da matrícula são exibidos corretamente ao clicar em "Visualizar". |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir matrícula cadastrada. |

| **Passos**                                                                                                              |
| :---------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de matrículas                                                                              |
| **QUANDO** clicarmos no botão "Visualizar" (lupa) de uma matrícula                                                      |
| **ENTÃO** o sistema deverá exibir os dados gerais, os dados da matrícula, os valores e a observação conforme o cadastro |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O sistema deve exibir os dados da matrícula iguais aos informados no cadastro. |

| **Resultado da execução**                                                             |
| :------------------------------------------------------------------------------------ |
| **Falhou.** O valor total permanece R$ 52,00 e a visualização exibe "Desconto 52,00". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/102e4688-1b02-4882-9547-e5ad043f5d93) |

---

### Caso de Teste 11: Cancelamento de matrícula.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C06-CT11 | Verificar se a matrícula é cancelada ao confirmar o cancelamento. |

| **Pré-condições**                                           |
| :---------------------------------------------------------- |
| O usuário deve estar autenticado e existir matrícula ativa. |

| **Passos**                                                                                |
| :---------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de matrículas                                                |
| **E** clicamos no botão "Cancelar" (X) de uma matrícula ativa                             |
| **E** informamos o motivo do cancelamento e clicamos em "Cancelar Matrícula"              |
| **QUANDO** confirmarmos a mensagem "Deseja cancelar essa matrícula?"                      |
| **ENTÃO** a matrícula deverá ser cancelada e deixar de constar entre as matrículas ativas |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema deve atualizar o status da matrícula para cancelado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/061cf202-9312-4566-a670-f50ed2fb27ac) |

---

### Caso de Teste 12: Exclusão de matrícula.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C06-CT12 | Verificar se a matrícula é excluída ao confirmar a exclusão. |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir matrícula cadastrada. |

| **Passos**                                                                                              |
| :------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de matrículas                                                              |
| **E** clicamos no botão "Deletar" (lixeira) de uma matrícula                                            |
| **QUANDO** confirmarmos a mensagem "Deseja deletar essa matrícula?"                                     |
| **ENTÃO** o sistema deverá exibir mensagem de sucesso e a matrícula não deverá mais constar na listagem |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| O sistema deve excluir a matrícula e informar o sucesso da operação. |

| **Resultado da execução**                                                                                                                                                                                 |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro no servidor - Erro interno inesperado." e a listagem não é atualizada (a matrícula continua aparecendo até a página ser recarregada), embora a exclusão seja efetivada. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/21646323-7507-4ece-a3b1-16ab9def23ef) |

---

### Caso de Teste 13: Data inválida na parcela da matrícula.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C06-CT13 | Verificar se o campo "Data" da janela "Quantidade Parcelas" aceita somente datas válidas. |

| **Pré-condições**                                                                   |
| :---------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e o formulário de matrícula deve estar preenchido. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que preenchemos o formulário de matrícula e clicamos em "Salvar" |
| **E** a janela "Quantidade Parcelas" é exibida                            |
| **QUANDO** informarmos a data inválida "2026/05/192" no campo "Data"      |
| **ENTÃO** o sistema deverá rejeitar a data informada                      |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| Somente datas válidas no padrão DD/MM/AAAA devem ser aceitas. |

| **Resultado da execução**                                   |
| :---------------------------------------------------------- |
| **Falhou.** O sistema aceita a data inválida "2026/05/192". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/02ee32cf-7b68-4011-9cd9-d0faaba8470e) |

---

### Caso de Teste 14: Conferir matrículas ativas com os clientes ativos.

| ID       | Descrição                                         |
| :------- | :------------------------------------------------ |
| C06-CT14 | As matrículas ativas pertencem a clientes ativos. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que estamos em `/matriculas` e anotamos as matrículas com status ATIVO |
| **QUANDO** abrimos `/clientes` com Status "Ativo"                               |
| **ENTÃO** os clientes das matrículas ativas aparecem como ativos                |

| **Critérios de aceitação**                                                  |
| :-------------------------------------------------------------------------- |
| A quantidade e os nomes dos clientes ativos batem com as matrículas ativas. |

| **Resultado da execução**                                                                                                                                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Em 15/11/2026, Matrículas mostra 5 ativas, entre elas 242 - Marcelo Longo Zandonadi e 241 - Rafaela Andrade. Em Clientes, esses dois cadastros aparecem como INATIVO (filtro Status "Inativo"), e o card de clientes ativos mostra 13. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3743daa3-da02-4939-bd85-1cbf634c797d) |

---

### Caso de Teste 16: Cadastro de matrícula com Dia Vencimento inválido.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C06-CT16 | O campo "Dia Vencimento" só aceita um dia do mês (1 a 31). |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/adicionar-matricula` com cliente, modalidade e tipo de pagamento preenchidos |
| **E** informamos "456456456" no campo "Dia Vencimento"                                                 |
| **QUANDO** clicarmos no botão "Salvar"                                                                 |
| **ENTÃO** o sistema informa que o dia de vencimento deve ser de 1 a 31                                 |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| O campo recusa valores fora de 1 a 31, sem mostrar erro do banco de dados. |

| **Resultado da execução**                                                                                                                                            |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O campo aceita "456456456" e "15/11/2026" e, ao salvar, aparece "Não foi possível concluir" com o erro de SQL "Data too long for column 'dia_venc_pag'". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a42460a4-3174-4773-b2c1-8763072bd960) |
