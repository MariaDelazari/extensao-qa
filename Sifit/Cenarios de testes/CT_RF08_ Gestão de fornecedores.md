## Cenário 08: Gestão de fornecedores na plataforma SIFIT.

### Caso de Teste 01: Acesso à listagem de fornecedores.

| ID       | Descrição                                                                                  |
| :------- | :----------------------------------------------------------------------------------------- |
| C08-CT01 | Verificar se a tela de fornecedores é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                       |
| :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                       |
| **QUANDO** acessarmos o menu "Fornecedores"                                                                                                      |
| **ENTÃO** a tela deverá exibir os filtros de busca, os indicadores (Fornecedores Cadastrados e Fornecedores Ativos) e a listagem de fornecedores |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de fornecedores com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/69d7efa4-7ef3-469d-b585-4dec4def49c7) |

---

### Caso de Teste 02: Busca de fornecedor pelo nome.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C08-CT02 | Verificar se a busca pelo nome retorna os fornecedores correspondentes, inclusive com nome parcial. |

| **Pré-condições**                                                                       |
| :-------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado com o nome pesquisado. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de fornecedores                          |
| **E** informamos "pesado" no campo "Nome"                             |
| **QUANDO** clicarmos no botão "Buscar"                                |
| **ENTÃO** a listagem deverá exibir somente o fornecedor "Peso Pesado" |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar a listagem pelo nome informado, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/51320744-ffac-4597-bea6-7a6a506840b5) |

---

### Caso de Teste 03: Busca de fornecedor pelo código.

| ID       | Descrição                                                             |
| :------- | :-------------------------------------------------------------------- |
| C08-CT03 | Verificar se a busca pelo código retorna o fornecedor correspondente. |

| **Pré-condições**                                                                         |
| :---------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado com o código pesquisado. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos na tela de fornecedores                    |
| **E** informamos "394" no campo "Código"                        |
| **QUANDO** clicarmos no botão "Buscar"                          |
| **ENTÃO** a listagem deverá exibir somente o fornecedor "Copel" |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| O sistema deve retornar o fornecedor correspondente ao código informado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/65fecda6-95e0-48e4-b5ce-8ae6aa041750) |

---

### Caso de Teste 04: Busca de fornecedor com código inexistente.

| ID       | Descrição                                                                                               |
| :------- | :------------------------------------------------------------------------------------------------------ |
| C08-CT04 | Verificar se o sistema informa que nenhum fornecedor foi encontrado ao pesquisar um código inexistente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                           |
| :------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de fornecedores                                                                         |
| **E** informamos "999" no campo "Código"                                                                             |
| **QUANDO** clicarmos no botão "Buscar"                                                                               |
| **ENTÃO** a listagem não deverá exibir fornecedores e o sistema deverá informar que nenhum fornecedor foi encontrado |

| **Critérios de aceitação**                                                        |
| :-------------------------------------------------------------------------------- |
| O sistema não deve exibir fornecedores que não correspondem ao código pesquisado. |

| **Resultado da execução**                                                                         |
| :------------------------------------------------------------------------------------------------ |
| **Falhou.** O sistema exibe "Erro no servidor" e a listagem continua com todos os 8 fornecedores. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7e669c65-5f1a-4cc5-b773-2062825d4618) |

---

### Caso de Teste 05: Salvar Fornecedores com o formulário vazio.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C08-CT05 | O cadastro de Fornecedores não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Novo Fornecedor" em `/fornecedores`             |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso passou: apareceu o aviso "Informe o nome do fornecedor." e o cadastro não foi salvo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/01f3c41f-cf4f-4bd8-be46-8dd4be1f13c7) |

---

### Caso de Teste 06: Cadastro de fornecedor com dados válidos.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C08-CT06 | Verificar se o fornecedor é cadastrado ao informar os dados corretamente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                              |
| :---------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Fornecedor"                                                                     |
| **E** informamos o nome "Fornecedor Teste Ville", um CNPJ válido, telefone, e-mail, estado "Paraná" e cidade "Umuarama" |
| **QUANDO** clicarmos no botão "Salvar"                                                                                  |
| **ENTÃO** o sistema deverá exibir mensagem de sucesso e o fornecedor deverá constar na listagem com status "ATIVO"      |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve cadastrar o fornecedor e exibi-lo na listagem. |

| **Resultado da execução**                                                                 |
| :---------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro ao salvar fornecedor." e o fornecedor não é cadastrado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2c2c4c60-b617-44b6-8337-1cc44e327fd9) |

---

### Caso de Teste 07: Visualização dos dados do fornecedor.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C08-CT07 | Verificar se os dados do fornecedor são exibidos ao clicar em "Visualizar". |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado. |

| **Passos**                                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de fornecedores                                                                          |
| **QUANDO** clicarmos no botão "Visualizar" (lupa) do fornecedor "Jasira Souzas"                                       |
| **ENTÃO** deverá ser exibida a janela "Visualizar Fornecedor" com os dados principais, documentos, contato e endereço |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve exibir os dados do fornecedor selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a883bf5b-f0a8-4747-b1bf-60b364abd224) |

---

### Caso de Teste 08: Alteração dos dados do fornecedor.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C08-CT08 | Verificar se as alterações nos dados do fornecedor são salvas corretamente. |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado. |

| **Passos**                                           |
| :--------------------------------------------------- |
| **DADO** que estamos visualizando o fornecedor "Jao" |
| **E** clicamos no ícone de edição                    |
| **E** alteramos o nome para "Jao Teste Ville"        |
| **QUANDO** clicarmos no botão "Salvar"               |
| **ENTÃO** a listagem deverá exibir o nome atualizado |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve salvar as alterações e exibi-las na listagem. |

| **Resultado da execução**                                                                 |
| :---------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro no servidor" e o fornecedor permanece com o nome "Jao". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1bd0c308-c44d-42f3-8560-57ce86b98b1b) |

---

### Caso de Teste 09: Cancelamento da exclusão de fornecedor.

| ID       | Descrição                                                                                                   |
| :------- | :---------------------------------------------------------------------------------------------------------- |
| C08-CT09 | Verificar se o sistema solicita confirmação antes de excluir um fornecedor e mantém o registro ao cancelar. |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| O usuário deve estar autenticado e existir fornecedor cadastrado. |

| **Passos**                                                                                         |
| :------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de fornecedores                                                       |
| **E** clicamos no botão "Deletar" (X) de um fornecedor                                             |
| **QUANDO** o sistema exibir a mensagem "Deseja deletar este fornecedor?" e clicarmos em "Cancelar" |
| **ENTÃO** o fornecedor deverá permanecer na listagem                                               |

| **Critérios de aceitação**                                                                   |
| :------------------------------------------------------------------------------------------- |
| O sistema deve solicitar confirmação e não excluir o fornecedor quando a ação for cancelada. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/cbe09523-b594-4d9f-b8f0-95b4e2c6bf0d) |
