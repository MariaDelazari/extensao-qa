## Cenário 04: Gestão de clientes.

### Caso de Teste 01: Acesso à listagem de clientes.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C04-CT01 | Verificar se a tela de clientes é exibida corretamente com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                     |
| **QUANDO** acessarmos o menu "Clientes"                                                                                                                        |
| **ENTÃO** a tela deverá exibir os filtros de busca, os indicadores (Clientes Cadastrados, Clientes Ativos, Sem Matrículas e Ausentes) e a listagem de clientes |

| **Critérios de aceitação**                                                                      |
| :---------------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de clientes com todos os seus componentes carregados corretamente. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/b1c527ff-d8b0-4c51-a962-a32348beab98) |

---

### Caso de Teste 02: Buscar cliente pelo nome.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C04-CT02 | A busca por nome aceita parte do nome e não diferencia maiúsculas de minúsculas. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                  |
| :---------------------------------------------------------- |
| **DADO** que estamos em `/clientes` com Status "Todos"      |
| **E** digitamos "mar" no campo Nome                         |
| **QUANDO** clicamos em "Buscar"                             |
| **ENTÃO** a lista mostra só clientes cujo nome contém "mar" |
| **E** repetindo com "MAR" a lista tem a mesma quantidade    |

| **Critérios de aceitação**                                                           |
| :----------------------------------------------------------------------------------- |
| A busca por nome filtra por parte do texto, sem diferenciar maiúsculas e minúsculas. |

| **Resultado da execução**                                                                                                                                                                                                                                                                           |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso passou: "mar" e "MAR" retornaram 17 clientes cada. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: retornou somente os clientes correspondentes ao nome pesquisado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1a48e93b-6754-48a9-8b3e-302281e1b967) |

---

### Caso de Teste 03: Busca de cliente com nome inexistente.

| ID       | Descrição                                                                                          |
| :------- | :------------------------------------------------------------------------------------------------- |
| C04-CT03 | Verificar se o sistema informa que nenhum cliente foi encontrado ao pesquisar um nome inexistente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de clientes                                                        |
| **E** informamos no campo "Nome" um nome que não está cadastrado                                |
| **QUANDO** clicarmos no botão "Buscar"                                                          |
| **ENTÃO** o sistema deverá apresentar uma mensagem informando que nenhum cliente foi encontrado |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa em vez de apenas uma tabela vazia. |

| **Resultado da execução**                                                                |
| :--------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1400615a-e41d-4ab8-95d5-5a68bd56510d) |

---

### Caso de Teste 04: Buscar cliente pelo código.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C04-CT04 | A busca por código retorna o cliente com aquele código. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                             |
| :----------------------------------------------------- |
| **DADO** que estamos em `/clientes` com Status "Todos" |
| **E** digitamos "242" no campo Código                  |
| **QUANDO** clicamos em "Buscar"                        |
| **ENTÃO** a lista mostra só o cliente de código 242    |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| A busca por código retorna apenas o cliente informado. |

| **Resultado da execução**                                                                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tela de clientes fica totalmente em branco após clicar em "Buscar", embora o cliente 408 esteja cadastrado e ativo. Em 28/10/2026, no Sifit Unialfa, o caso passou: a lista mostrou uma linha: 242 - Ricardo Ford. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e36fb928-6b21-4210-b361-cc99a1358cf9) |

---

### Caso de Teste 05: Listar clientes e conferir a paginação.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C04-CT05 | A listagem de clientes mostra a paginação de acordo com o resultado do filtro. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/clientes` com o filtro Status "Ativo" (padrão)                       |
| **QUANDO** a listagem terminar de carregar                                                     |
| **ENTÃO** a tabela mostra os clientes ativos e o card "Clientes Ativos" tem a mesma quantidade |
| **E** a paginação só oferece as páginas que têm clientes                                       |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| A listagem e a paginação refletem o resultado do filtro aplicado. |

| **Resultado da execução**                                                                                                                                                                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** A paginação mostra 3 páginas para 1 resultado; a página 2 lista clientes que não correspondem à busca. Em 28/10/2026, no Sifit Unialfa, o caso falhou: a tabela mostra 1 cliente (408 - Lila) e o card "Clientes Ativos" mostra 1, mas a paginação oferece as páginas 1, 2 e 3. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2359f24c-548d-4136-b968-1234c3f2770e) |

---

### Caso de Teste 06: Quantidade de registros por página.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C04-CT06 | Verificar se a listagem respeita a quantidade de registros por página selecionada. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem mais de 50 clientes cadastrados. |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que estamos na tela de clientes com a opção "50" registros por página |
| **E** selecionamos a opção "Todos" no filtro "Status"                          |
| **QUANDO** clicarmos no botão "Buscar"                                         |
| **ENTÃO** a primeira página deverá exibir no máximo 50 clientes                |

| **Critérios de aceitação**                                                          |
| :---------------------------------------------------------------------------------- |
| O sistema deve limitar a listagem à quantidade de registros por página selecionada. |

| **Resultado da execução**                                                                       |
| :---------------------------------------------------------------------------------------------- |
| **Falhou.** A primeira página exibe todos os clientes cadastrados (125 no momento da gravação). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7e9313e8-1a42-4e1f-99be-f22711d0d555) |

---

### Caso de Teste 07: Cadastrar cliente com campos obrigatórios vazios.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C04-CT07 | O cadastro de cliente não segue com os campos obrigatórios vazios. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que estamos na tela "Cadastrar Cliente" (`/adicionar-cliente`) |
| **E** deixamos Nome, Sexo e Data de Nascimento vazios                   |
| **QUANDO** clicamos em "Cadastrar Cliente"                              |
| **ENTÃO** o sistema avisa que falta preencher e permanece na tela       |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O cadastro é bloqueado e a tela informa o campo que falta. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso passou: o sistema permaneceu em `/adicionar-cliente`, não enviou requisição e mostrou "Preencha o nome da pessoa". Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: cadastro bloqueado; a validação é exibida um campo obrigatório por vez. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/b2527661-b09d-4792-b31d-a0e24e09bdc0) |

---

### Caso de Teste 08: Cadastro de cliente com dados válidos.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C04-CT08 | Verificar se o cliente é cadastrado ao informar todos os dados corretamente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                            |
| :---------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Cadastrar Cliente"                                                      |
| **E** informamos o nome "Teste Ville Nunes", o status "Ativo", o sexo e uma data de nascimento válida |
| **QUANDO** clicarmos no botão "Cadastrar Cliente"                                                     |
| **ENTÃO** o sistema deverá exibir mensagem de sucesso e o cliente deverá constar na listagem          |

| **Critérios de aceitação**                                             |
| :--------------------------------------------------------------------- |
| O sistema deve cadastrar o cliente e exibi-lo na listagem de clientes. |

| **Resultado da execução**                                                                         |
| :------------------------------------------------------------------------------------------------ |
| **Falhou.** O sistema exibe o modal "Erro - Erro ao criar cliente." e o cliente não é cadastrado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e21003f6-a3e5-4f6f-9ea2-755f25b7ff91) |

---

### Caso de Teste 09: Visualização dos dados do cliente.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C04-CT09 | Verificar se a tela de detalhes do cliente é exibida ao clicar em "Visualizar". |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de clientes                                                             |
| **QUANDO** clicarmos no botão "Visualizar" (lupa) de um cliente                                      |
| **ENTÃO** deveremos ser direcionados à tela "Visualizar Cliente" com os dados do cliente selecionado |

| **Critérios de aceitação**                                                                                |
| :-------------------------------------------------------------------------------------------------------- |
| O sistema deve exibir os dados, o desempenho, a matrícula e a situação financeira do cliente selecionado. |

| **Resultado da execução**                                                             |
| :------------------------------------------------------------------------------------ |
| **Falhou.** O sistema exibe "Erro no servidor - Erro interno inesperado." (erro 500). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/aa6dbfa6-1c39-4d8a-b536-86d4b806198e) |

---

### Caso de Teste 10: Alteração dos dados do cliente.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C04-CT10 | Verificar se as alterações nos dados do cliente são salvas corretamente. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Visualizar Cliente"                                                      |
| **E** clicamos no botão "Alterar dados"                                                                |
| **E** alteramos o nome do cliente para "Teste Ville Nunes"                                             |
| **QUANDO** clicarmos no botão "Salvar Alterações"                                                      |
| **ENTÃO** o sistema deverá exibir mensagem de sucesso e a listagem deverá apresentar o nome atualizado |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve salvar as alterações e exibi-las na listagem e nos detalhes do cliente. |

| **Resultado da execução**                                                                                                                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe o modal "Erro - Erro ao criar cliente." e o cliente permanece com os dados anteriores. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: nome e data atualizados e persistidos. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ef0c7a28-0a2f-4bb6-9c78-3fc0995ec51f) |

---

### Caso de Teste 11: Cancelamento da exclusão de cliente.

| ID       | Descrição                                                                                                |
| :------- | :------------------------------------------------------------------------------------------------------- |
| C04-CT11 | Verificar se o sistema solicita confirmação antes de excluir um cliente e mantém o registro ao cancelar. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de clientes                                                        |
| **E** clicamos no botão "Deletar" (X) de um cliente                                             |
| **QUANDO** o sistema exibir a mensagem "Deseja deletar este cliente?" e clicarmos em "Cancelar" |
| **ENTÃO** o cliente deverá permanecer na listagem                                               |

| **Critérios de aceitação**                                                                                  |
| :---------------------------------------------------------------------------------------------------------- |
| O sistema deve solicitar confirmação antes da exclusão e não remover o cliente quando a ação for cancelada. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a0153288-ba95-4015-852c-17228345f666) |

---

### Caso de Teste 12: Cadastro de cliente com data de nascimento futura.

| ID       | Descrição                                                                                          |
| :------- | :------------------------------------------------------------------------------------------------- |
| C04-CT12 | Verificar se o sistema impede o cadastro de cliente com data de nascimento posterior à data atual. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Cliente"                                     |
| **E** informamos o nome "Cliente Teste Ville", o status "Ativo" e o sexo "Masculino" |
| **E** informamos a data de nascimento 31/12/2027                                     |
| **QUANDO** clicarmos no botão "Cadastrar Cliente"                                    |
| **ENTÃO** o sistema deverá rejeitar a data futura                                    |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O cadastro deve ser bloqueado com uma mensagem de data inválida. |

| **Resultado da execução**                                        |
| :--------------------------------------------------------------- |
| **Falhou.** Cliente cadastrado; a ficha exibe a idade "-2 anos". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f3cd80a9-c549-4e43-8957-182eaa983f3d) |

---

### Caso de Teste 13: Cadastro de cliente com CPF inválido.

| ID       | Descrição                                                                                        |
| :------- | :----------------------------------------------------------------------------------------------- |
| C04-CT13 | Verificar se o sistema valida o dígito verificador do CPF no cadastro e na alteração do cliente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos no cadastro ou na alteração de um cliente        |
| **E** informamos o CPF "111.111.111-11"                               |
| **QUANDO** clicarmos em "Cadastrar Cliente" ou "Salvar Alterações"    |
| **ENTÃO** o sistema deverá informar que o CPF é inválido e não salvar |

| **Critérios de aceitação**         |
| :--------------------------------- |
| O CPF inválido deve ser rejeitado. |

| **Resultado da execução**                              |
| :----------------------------------------------------- |
| **Falhou.** CPF 111.111.111-11 salvo sem nenhum aviso. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/aee4435d-fdbd-4a84-bfe5-d8a28801ecd7) |

---

### Caso de Teste 14: Filtro de clientes pelo status "Ativo".

| ID       | Descrição                                                                             |
| :------- | :------------------------------------------------------------------------------------ |
| C04-CT14 | Verificar se, com o filtro "Status" em "Ativo", somente clientes ativos são listados. |

| **Pré-condições**                                                        |
| :----------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem clientes ativos e inativos. |

| **Passos**                                                  |
| :---------------------------------------------------------- |
| **DADO** que estamos na listagem de clientes                |
| **E** o filtro "Status" está em "Ativo"                     |
| **QUANDO** a listagem for exibida                           |
| **ENTÃO** nenhum cliente com status INATIVO deverá aparecer |

| **Critérios de aceitação**                  |
| :------------------------------------------ |
| Somente clientes ativos devem ser listados. |

| **Resultado da execução**                                                      |
| :----------------------------------------------------------------------------- |
| **Falhou.** A lista exibe clientes com status INATIVO com o filtro em "Ativo". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a6adccf3-ae4c-47f8-9343-8ad793e5758e) |

---

### Caso de Teste 15: Visualização da ficha de cliente recém-cadastrado.

| ID       | Descrição                                                                                      |
| :------- | :--------------------------------------------------------------------------------------------- |
| C04-CT15 | Verificar se a ficha do cliente exibe apenas dados reais, sem "null" ou informações fictícias. |

| **Pré-condições**                                                        |
| :----------------------------------------------------------------------- |
| Deve existir um cliente de teste cadastrado sem telefone e sem endereço. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que estamos na listagem de clientes                                                  |
| **QUANDO** clicarmos em "Visualizar" no cliente de teste                                      |
| **ENTÃO** os campos sem informação deverão aparecer em branco ou com "-", sem dados fictícios |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| A ficha não deve exibir "null" nem dados que não foram cadastrados. |

| **Resultado da execução**                                                                                                                                                                                    |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O telefone aparece como "null"; o Bairro aparece como "null" na edição; o card "Objetivos" exibe "Perda de peso e ganho de resistência" e "Progresso geral 60%" para um cliente sem nenhum dado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a4c73bde-5ac1-43ad-8a47-3ebde1f4e346) |

---

### Caso de Teste 16: Digitar letras no campo Código.

| ID       | Descrição                                  |
| :------- | :----------------------------------------- |
| C04-CT16 | O campo Código da busca só aceita números. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                 |
| :----------------------------------------- |
| **DADO** que estamos em `/clientes`        |
| **QUANDO** digitamos "abc" no campo Código |
| **ENTÃO** o campo não aceita as letras     |

| **Critérios de aceitação**                            |
| :---------------------------------------------------- |
| O campo Código recusa caracteres que não são números. |

| **Resultado da execução**                            |
| :--------------------------------------------------- |
| **Falhou.** O campo aceitou e manteve o texto "abc". |

| **Evidência(s)**               |
| :----------------------------- |
| [PENDENTE VÍDEO] (roteiro V07) |
