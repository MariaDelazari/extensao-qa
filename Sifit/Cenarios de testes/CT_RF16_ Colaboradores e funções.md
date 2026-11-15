## Cenário 16: Colaboradores e funções.

### Caso de Teste 01: Acesso à listagem de colaboradores.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C16-CT01 | Verificar se a tela de colaboradores é exibida com a busca, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                        |
| :-------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                        |
| **QUANDO** acessarmos o menu "Colaboradores"                                                                                      |
| **ENTÃO** a tela deverá exibir a busca, os indicadores (Colaboradores Cadastrados, Colaboradores Ativos e Personais) e a listagem |

| **Critérios de aceitação**                                                              |
| :-------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de colaboradores com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/8918e423-b497-4e6b-984b-e82fc5700e75) |

---

### Caso de Teste 02: Busca de colaborador pelo nome.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C16-CT02 | Verificar se a busca pelo nome retorna os colaboradores correspondentes. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem colaboradores cadastrados. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de colaboradores                                   |
| **E** informamos "erika" no campo "Nome"                                        |
| **QUANDO** clicarmos no botão "Buscar"                                          |
| **ENTÃO** a listagem deverá exibir somente os colaboradores com "Erika" no nome |

| **Critérios de aceitação**                                                                         |
| :------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar os colaboradores pelo nome, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/646eeecf-b173-44b1-aa63-a79a13d598eb) |

---

### Caso de Teste 03: Busca de colaborador com código inexistente.

| ID       | Descrição                                                             |
| :------- | :-------------------------------------------------------------------- |
| C16-CT03 | Verificar se o sistema informa que nenhum colaborador foi encontrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que estamos na tela de colaboradores                             |
| **E** informamos "999" no campo "Código"                                  |
| **QUANDO** clicarmos no botão "Buscar"                                    |
| **ENTÃO** o sistema deverá informar que nenhum colaborador foi encontrado |

| **Critérios de aceitação**                                                |
| :------------------------------------------------------------------------ |
| O sistema deve exibir uma mensagem informativa em vez de uma linha vazia. |

| **Resultado da execução**                             |
| :---------------------------------------------------- |
| **Falhou.** A listagem exibe uma linha vazia com "/". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/fd885338-b1b1-4689-8a94-a0de9885af05) |

---

### Caso de Teste 04: Cadastrar colaborador com campos vazios.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C16-CT04 | O colaborador não é salvo com os campos vazios e o sistema orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                             |
| :--------------------------------------------------------------------- |
| **DADO** que estamos em "Novo Colaborador" (`/adicionar-colaborador`)  |
| **E** deixamos os campos vazios                                        |
| **QUANDO** clicamos em "Salvar"                                        |
| **ENTÃO** o sistema informa os campos que faltam, sem erro de servidor |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução**                                                                                                                                 |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao salvar o colaborador sem preencher nada, a tela mostrou "Erro no servidor. Erro interno inesperado." e não indicou os campos obrigatórios. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/fa03cb2a-8ed4-45cf-a70a-6a8a999ab4da) |

---

### Caso de Teste 05: Cadastro de colaborador com dados válidos.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C16-CT05 | Verificar se o colaborador é cadastrado ao informar os dados corretamente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                     |
| :------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela "Novo Colaborador"                                                               |
| **E** informamos o nome "Colaborador Teste Ville", selecionamos o Status "Ativo" e o Sexo "Masculino"          |
| **E** informamos data de nascimento, CPF, e-mail, login, senha e celular válidos                               |
| **QUANDO** clicarmos no botão "Salvar"                                                                         |
| **ENTÃO** o colaborador deverá constar na listagem com status "ATIVO" e os indicadores deverão ser atualizados |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| O sistema deve cadastrar o colaborador e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/7497e363-2789-4cb4-9098-2ee4d423c3e7) |

---

### Caso de Teste 06: Cadastro de colaborador sem alterar Status e Sexo.

| ID       | Descrição                                                                                     |
| :------- | :-------------------------------------------------------------------------------------------- |
| C16-CT06 | Verificar se o cadastro funciona com os valores exibidos por padrão nos campos Status e Sexo. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que acessamos a tela "Novo Colaborador"                      |
| **E** os campos Status e Sexo exibem "Ativo" e "Masculino"            |
| **E** preenchemos os demais dados válidos sem alterar Status e Sexo   |
| **QUANDO** clicarmos no botão "Salvar"                                |
| **ENTÃO** o colaborador deverá ser cadastrado com os valores exibidos |

| **Critérios de aceitação**                                                |
| :------------------------------------------------------------------------ |
| Os valores exibidos nos campos devem ser os valores enviados no cadastro. |

| **Resultado da execução**                                                                                    |
| :----------------------------------------------------------------------------------------------------------- |
| **Falhou.** Salvando sem escolher Status e Sexo, a tela mostra "Erro no servidor. Erro interno inesperado.". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/4e8caa28-0972-44c6-b4e8-34fb85ac989d) |

---

### Caso de Teste 07: Alteração de colaborador.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C16-CT07 | Verificar se os dados do colaborador podem ser alterados. |

| **Pré-condições**                                                                   |
| :---------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o colaborador "Colaborador Teste Ville". |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que acessamos o perfil do colaborador "Colaborador Teste Ville" e clicamos em "Editar" |
| **E** alteramos o nome para "Colaborador Teste Ville Editado"                                   |
| **QUANDO** clicarmos no botão "Salvar"                                                          |
| **ENTÃO** a listagem deverá exibir o nome atualizado                                            |

| **Critérios de aceitação**                          |
| :-------------------------------------------------- |
| O sistema deve salvar as alterações do colaborador. |

| **Resultado da execução**                                                                               |
| :------------------------------------------------------------------------------------------------------ |
| **Falhou.** Ao salvar a alteração, o DevTools (aba Network) mostra comandos SQL na resposta do sistema. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/4c015a99-0c38-4e9d-a68b-3e38d60df197) |
| [Print](../Evidencias/C16-CT07.png) |

---

### Caso de Teste 08: Inativação de colaborador.

| ID       | Descrição                               |
| :------- | :-------------------------------------- |
| C16-CT08 | Verificar se o colaborador é inativado. |

| **Pré-condições**                                                      |
| :--------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir colaborador de teste ativo. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de edição do colaborador de teste                                                  |
| **E** selecionamos "Inativo" no campo "Status"                                                                  |
| **QUANDO** clicarmos no botão "Salvar"                                                                          |
| **ENTÃO** o colaborador deverá constar como "INATIVO" e o indicador "Colaboradores Ativos" deverá diminuir em 1 |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve inativar o colaborador e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/9427e088-d278-4bf3-adbf-38145550d055) |

---

### Caso de Teste 09: Vínculo de função ao colaborador.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C16-CT09 | Verificar se uma função pode ser vinculada ao colaborador. |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir colaborador de teste. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que clicamos no botão "Funções" do colaborador de teste      |
| **E** selecionamos a função "Atendente"                               |
| **QUANDO** clicarmos em "Adicionar"                                   |
| **ENTÃO** a função "Atendente" deverá constar em "Funções vinculadas" |

| **Critérios de aceitação**                       |
| :----------------------------------------------- |
| O sistema deve vincular a função ao colaborador. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/e9a554e5-d99d-45e5-ae9d-7705448c4536) |

---

### Caso de Teste 10: Exclusão de colaborador.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C16-CT10 | Verificar se o colaborador é excluído ao confirmar a exclusão. |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir colaborador de teste. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de colaboradores                         |
| **E** clicamos no botão "Deletar" do colaborador de teste             |
| **QUANDO** confirmarmos a mensagem "Deseja deletar este colaborador?" |
| **ENTÃO** o colaborador não deverá mais constar na listagem           |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve solicitar confirmação e excluir o colaborador. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/42190ad4-dbbd-4064-9b7f-25a8c468b64a) |

---

### Caso de Teste 11: Acesso à tela de funções.

| ID       | Descrição                                                                             |
| :------- | :------------------------------------------------------------------------------------ |
| C16-CT11 | Verificar se a tela de funções é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                    |
| :---------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                    |
| **QUANDO** acessarmos o menu "Funções"                                                                                        |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Funções, Internas, Personal e Avaliadores) e a listagem de funções |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de funções com indicadores coerentes com a listagem. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/753b282c-0dd6-4175-83e1-d99b4d719b9b) |

---

### Caso de Teste 12: Filtro de funções por tipo.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C16-CT12 | Verificar se o filtro "Tipo" exibe somente as funções do tipo selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                           |
| :------------------------------------------------------------------- |
| **DADO** que estamos na tela de funções                              |
| **E** selecionamos "Externo" no filtro "Tipo"                        |
| **QUANDO** clicarmos no botão "Buscar"                               |
| **ENTÃO** a listagem deverá exibir somente funções do tipo "Externo" |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve filtrar as funções pelo tipo selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/9eef811c-978a-46a7-8187-9a23d251ea88) |

---

### Caso de Teste 13: Cadastro de função sem nome.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C16-CT13 | Verificar se o sistema impede o cadastro de função sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Nova Função"                                           |
| **E** mantemos o campo "Nome" vazio                                                   |
| **QUANDO** clicarmos no botão "Salvar Função"                                         |
| **ENTÃO** o sistema deverá solicitar o preenchimento do nome ("Preencha este campo.") |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o nome seja informado. |

| **Resultado da execução**                                                                                                                                                                                                                                        |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/9e3bb636-5c64-407d-a73e-295a47022426) |

---

### Caso de Teste 14: Cadastro de função com dados válidos.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C16-CT14 | Verificar se a função é cadastrada e os indicadores são atualizados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                  |
| :---------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Nova Função"                                                                 |
| **E** informamos o nome "Função Testes Ville", o tipo "Externo" e Personal "Sim"                             |
| **QUANDO** clicarmos no botão "Salvar Função"                                                               |
| **ENTÃO** a função deverá constar na listagem e os indicadores "Funções" e "Personal" deverão aumentar em 1 |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve cadastrar a função e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/79433cc8-2a6c-461a-bbbb-d088d8aaa307) |

---

### Caso de Teste 15: Cadastro de função duplicada.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C16-CT15 | Verificar se o sistema impede o cadastro de função com nome já existente. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir a função "Função Teste Ville". |

| **Passos**                                                     |
| :------------------------------------------------------------- |
| **DADO** que a função "Função Testes Ville" já está cadastrada  |
| **E** abrimos a janela "Nova Função" e informamos o mesmo nome |
| **QUANDO** clicarmos no botão "Salvar Função"                  |
| **ENTÃO** o sistema deverá informar que a função já existe     |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O sistema não deve permitir funções duplicadas. |

| **Resultado da execução**                         |
| :------------------------------------------------ |
| **Falhou.** A função é cadastrada em duplicidade. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/05a2cb17-c81f-45f1-a9be-05fa709d4f82) |

---

### Caso de Teste 16: Alteração e exclusão de função.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C16-CT16 | Verificar se é possível alterar ou excluir uma função cadastrada. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir a função "Função Teste Ville". |

| **Passos**                                                                                                       |
| :--------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de funções                                                                          |
| **QUANDO** clicarmos em "Visualizar" da função "Função Teste Ville" e procurarmos as opções de edição e exclusão |
| **ENTÃO** o sistema deverá permitir alterar os dados da função e excluí-la                                       |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| O sistema deve permitir alterar e excluir funções. |

| **Resultado da execução**                                             |
| :-------------------------------------------------------------------- |
| **Falhou.** Os campos são somente leitura e não há opção de exclusão. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/cf5d18c4-dc37-4ca9-af67-469cb7f230d2) |

---

### Caso de Teste 17: Permissões da função.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C16-CT17 | Verificar se as permissões de uma função podem ser marcadas e são mantidas. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir a função "Função Teste Ville". |

| **Passos**                                                                   |
| :--------------------------------------------------------------------------- |
| **DADO** que clicamos no botão "Permissões" da função "Função Teste Ville"   |
| **E** marcamos a permissão "Entrar em Administrativo" e clicamos em "Salvar" |
| **QUANDO** abrirmos novamente as permissões da função                        |
| **ENTÃO** a permissão "Entrar em Administrativo" deverá continuar marcada    |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| O sistema deve salvar as permissões da função. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/d6fe6b79-b073-45ce-aec5-1291e7f3dd64) |
