## Cenário 31: Categorias de Conta a Pagar na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Categorias de Conta a Pagar.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C31-CT01 | Verificar se a tela de categorias pode ser acessada pelo menu do sistema. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                    |
| **QUANDO** procurarmos "Categorias de Conta a Pagar" no menu lateral, inclusive em Financeiro |
| **ENTÃO** deverá existir um item que abre a tela com o menu lateral e o cabeçalho             |

| **Critérios de aceitação**                                                              |
| :-------------------------------------------------------------------------------------- |
| O sistema deve oferecer acesso à tela de categorias pelo menu, dentro do layout padrão. |

| **Resultado da execução**                                                                                                                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. A tela completa só abre pelo link /categorias-conta-pagar, sem o menu lateral e sem o cabeçalho. Em Contas a Pagar → Nova Conta, o botão "ADD CAT" abre só a janela "Adicionar Categoria", com o campo nome. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/5fe27a74-c994-4c78-9906-aaae1ba17b39) |

---

### Caso de Teste 02: Listagem de categorias.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C31-CT02 | Verificar se a tela exibe as categorias cadastradas. |

| **Pré-condições**                                                                                        |
| :------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT.                                                    |
| Devem existir categorias cadastradas (ex.: "Contas do dia a dia").                                       |
| A tela não tem item no menu: acessar pelo link https://sifitalfa.centrion.com.br/categorias-conta-pagar. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos autenticados no SIFIT                          |
| **QUANDO** acessarmos a tela Categorias de Conta a Pagar            |
| **ENTÃO** a listagem deverá exibir o código e o nome das categorias |

| **Critérios de aceitação**                       |
| :----------------------------------------------- |
| O sistema deve listar as categorias cadastradas. |

| **Resultado da execução**                                                                                                                                                                                                     |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A listagem aparece vazia, só com os títulos das colunas. No DevTools (aba Network), a API (/categoria-contas-pagar) retorna as categorias cadastradas, que também aparecem no campo "Categoria" da conta a pagar. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/8803140b-f4b4-4e45-b612-a4bb026a45ac) |

---

### Caso de Teste 03: Salvar categoria vazia.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C31-CT03 | Verificar se o sistema impede o cadastro de categoria sem nome. |

| **Pré-condições**                                                                                        |
| :------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT.                                                    |
| A tela não tem item no menu: acessar pelo link https://sifitalfa.centrion.com.br/categorias-conta-pagar. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Categorias de Conta a Pagar                             |
| **E** deixamos o campo "Nome" vazio                                                  |
| **QUANDO** clicarmos em "Salvar"                                                     |
| **ENTÃO** o sistema deverá informar que o nome é obrigatório e não criar a categoria |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve impedir o cadastro e informar o campo obrigatório. |

| **Resultado da execução**                                            |
| :------------------------------------------------------------------- |
| **Falhou.** Nenhuma mensagem aparece e a categoria é salva sem nome. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/9e6b78ae-531e-49b3-8b84-15cf25b861f1) |

---

### Caso de Teste 04: Cadastro de categoria com dados válidos.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C31-CT04 | Verificar se a categoria é cadastrada e fica disponível na conta a pagar. |

| **Pré-condições**                                                                                        |
| :------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT.                                                    |
| A tela não tem item no menu: acessar pelo link https://sifitalfa.centrion.com.br/categorias-conta-pagar. |

| **Passos**                                                                                        |
| :------------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela Categorias de Conta a Pagar                                          |
| **E** informamos o nome "Categoria Teste Ville"                                                   |
| **QUANDO** clicarmos em "Salvar"                                                                  |
| **ENTÃO** a categoria deverá ficar disponível no campo "Categoria" de Contas a Pagar → Nova Conta |

| **Critérios de aceitação**                                                      |
| :------------------------------------------------------------------------------ |
| O sistema deve cadastrar a categoria e oferecê-la no cadastro de conta a pagar. |

| **Resultado da execução**                                                                                                                                                                                  |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A categoria 26 "Categoria Teste Ville" foi criada e aparece no campo "Categoria" da nova conta a pagar. Não aparece mensagem de sucesso, e ela não aparece na listagem da tela (ver C31-CT02). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/3412258c-7bc9-43bc-a62e-e39b4a45e862) |

---

### Caso de Teste 05: Cadastro de categoria duplicada.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C31-CT05 | Verificar se o sistema impede categoria com nome já cadastrado. |

| **Pré-condições**                                                                                        |
| :------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT.                                                    |
| Deve existir a categoria "Categoria Teste Ville".                                                        |
| A tela não tem item no menu: acessar pelo link https://sifitalfa.centrion.com.br/categorias-conta-pagar. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que a categoria "Categoria Teste Ville" já está cadastrada |
| **E** informamos o mesmo nome                                       |
| **QUANDO** clicarmos em "Salvar"                                    |
| **ENTÃO** o sistema deverá informar que a categoria já existe       |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve impedir o cadastro de categoria duplicada. |

| **Resultado da execução**                                                       |
| :------------------------------------------------------------------------------ |
| **Falhou.** A categoria é salva de novo com o mesmo nome, sem nenhuma mensagem. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/4f5e6f3b-1d3d-4ecf-88a2-40e3019b5a2c) |
