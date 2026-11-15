## Cenário 33: Modelos e categorias de anamnese na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de categorias de anamnese.

| ID       | Descrição                                                                                              |
| :------- | :----------------------------------------------------------------------------------------------------- |
| C33-CT01 | Verificar se a tela de categorias de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                              |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                              |
| **QUANDO** clicarmos em "Categorias" no grupo Saúde do menu lateral                                                                                                                     |
| **ENTÃO** a tela "Categorias de Anamnese" deverá abrir com a busca "Buscar categoria...", os indicadores Total, Ativas, Inativas e Com perguntas, o botão "Nova Categoria" e a listagem |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A tela de categorias abre pelo menu com todos os seus componentes. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Salvar categoria com o formulário vazio.

| ID       | Descrição                                                                           |
| :------- | :---------------------------------------------------------------------------------- |
| C33-CT02 | Verificar se o sistema impede o cadastro de categoria sem nome e orienta o usuário. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Nova Categoria"                                             |
| **E** não preenchemos o campo "Nome da Categoria"                                     |
| **QUANDO** clicarmos no botão "Criar Categoria"                                       |
| **ENTÃO** o sistema deverá informar que o nome é obrigatório e não salvar a categoria |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| A categoria não é salva sem nome e a tela mostra o que falta. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Cadastro de categoria com dados válidos.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT03 | Verificar se a categoria é salva e aparece na listagem. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                                              |
| :------------------------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Nova Categoria"                                                               |
| **E** informamos o nome "Categoria Teste Maria", o ícone "bi-heart", uma cor e o status Ativo           |
| **QUANDO** clicarmos no botão "Criar Categoria"                                                         |
| **ENTÃO** a categoria deverá aparecer na listagem e os indicadores Total e Ativas deverão aumentar em 1 |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A categoria é salva com os dados informados e aparece na listagem. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastro de categoria duplicada.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C33-CT04 | Verificar se o sistema impede cadastrar duas categorias com o mesmo nome. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| Existir a categoria "Categoria Teste Maria", cadastrada no C33-CT03. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Categoria"                                        |
| **E** informamos o nome "Categoria Teste Maria"                                  |
| **QUANDO** clicarmos no botão "Criar Categoria"                                  |
| **ENTÃO** o sistema deverá informar que a categoria já existe e não salvar outra |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema não permite duas categorias com o mesmo nome. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Busca de categoria pelo nome.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C33-CT05 | Verificar se a busca filtra as categorias pelo nome. |

| **Pré-condições**                            |
| :------------------------------------------- |
| Existir a categoria "Categoria Teste Maria". |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Categorias de Anamnese"                          |
| **QUANDO** digitarmos "Teste Maria" no campo "Buscar categoria..."             |
| **ENTÃO** a listagem deverá mostrar só as categorias com "Teste Maria" no nome |

| **Critérios de aceitação**                                              |
| :---------------------------------------------------------------------- |
| A busca mostra apenas as categorias que correspondem ao texto digitado. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Alteração de categoria.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT06 | Verificar se a categoria pode ser alterada e inativada. |

| **Pré-condições**                            |
| :------------------------------------------- |
| Existir a categoria "Categoria Teste Maria". |

| **Passos**                                                                                                     |
| :------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Editar" na categoria "Categoria Teste Maria"                                         |
| **E** alteramos o status para Inativo                                                                          |
| **QUANDO** salvarmos a alteração                                                                               |
| **ENTÃO** a categoria deverá aparecer como Inativo, e os indicadores Ativas e Inativas deverão ser atualizados |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A alteração é salva e aparece na listagem e nos indicadores. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Exclusão de categoria.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C33-CT07 | Verificar se a categoria é excluída ao confirmar a exclusão. |

| **Pré-condições**                            |
| :------------------------------------------- |
| Existir a categoria "Categoria Teste Maria". |

| **Passos**                                                                             |
| :------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Excluir" na categoria "Categoria Teste Maria"                |
| **QUANDO** confirmarmos a mensagem "Excluir a categoria "Categoria Teste Maria"?"      |
| **ENTÃO** a categoria deverá sair da listagem e o indicador Total deverá diminuir em 1 |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| A categoria é excluída somente após a confirmação. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Acesso à tela de modelos de anamnese.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C33-CT08 | Verificar se a tela de modelos de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                                       |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                       |
| **QUANDO** clicarmos em "Modelos" no grupo Saúde do menu lateral                                                                                                                                 |
| **ENTÃO** a tela "Modelos de Anamnese" deverá abrir com a busca "Buscar modelo...", os indicadores Total de modelos, Ativos, Média de perguntas e Aplicações, o botão "Novo Modelo" e a listagem |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| A tela de modelos abre pelo menu com todos os seus componentes. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Salvar modelo sem nome.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C33-CT09 | Verificar se o sistema impede o cadastro de modelo sem nome e orienta o usuário. |

| **Pré-condições**                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Modelos de Anamnese" está aberta. |

| **Passos**                                                                         |
| :--------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo"                                             |
| **E** não preenchemos o campo "Nome do Modelo"                                     |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                      |
| **ENTÃO** o sistema deverá informar que o nome é obrigatório e não salvar o modelo |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O modelo não é salvo sem nome e a tela mostra o que falta. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Cadastro de modelo com pergunta.

| ID       | Descrição                                                                                        |
| :------- | :----------------------------------------------------------------------------------------------- |
| C33-CT10 | Verificar se o modelo é salvo com a pergunta escolhida e mostra a quantidade certa de perguntas. |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| Existir a pergunta "Manual SIFIT Lesão" em Perguntas de anamnese. |

| **Passos**                                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo"                                                                             |
| **E** informamos o nome "Modelo Teste Maria" e uma descrição                                                       |
| **E** adicionamos a pergunta "Manual SIFIT Lesão" e a marcamos como Obrigatória                                    |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                                      |
| **ENTÃO** o modelo deverá aparecer na listagem com 1 pergunta, e o indicador Total de modelos deverá aumentar em 1 |

| **Critérios de aceitação**                                                |
| :------------------------------------------------------------------------ |
| O modelo é salvo com a pergunta escolhida e a listagem mostra 1 pergunta. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Preview do modelo "Triplet".

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C33-CT11 | Verificar se o preview mostra as perguntas que o card do modelo informa. |

| **Pré-condições**                                   |
| :-------------------------------------------------- |
| Existir o modelo "Triplet", que informa 1 pergunta. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Modelos de Anamnese"                                   |
| **QUANDO** clicarmos em "Preview" no modelo "Triplet"                                |
| **ENTÃO** a janela deverá mostrar o nome, a descrição e a pergunta informada no card |

| **Critérios de aceitação**                                                   |
| :--------------------------------------------------------------------------- |
| O preview lista a mesma quantidade de perguntas informada no card do modelo. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 12: Alteração de modelo.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C33-CT12 | Verificar se o modelo pode ser alterado e inativado. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| Existir o modelo "Modelo Teste Maria", cadastrado no C33-CT10. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Editar" no modelo "Modelo Teste Maria"                                                  |
| **E** alteramos a descrição e o status para Inativo                                                               |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                                     |
| **ENTÃO** o modelo deverá aparecer como Inativo e com a nova descrição, e o indicador Ativos deverá diminuir em 1 |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A alteração é salva e aparece na listagem e nos indicadores. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 13: Exclusão de modelo.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C33-CT13 | Verificar se o modelo é excluído ao confirmar a exclusão. |

| **Pré-condições**                      |
| :------------------------------------- |
| Existir o modelo "Modelo Teste Maria". |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Excluir" no modelo "Modelo Teste Maria"                              |
| **QUANDO** confirmarmos a mensagem "Excluir o modelo "Modelo Teste Maria"?"                    |
| **ENTÃO** o modelo deverá sair da listagem e o indicador Total de modelos deverá diminuir em 1 |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O modelo é excluído somente após a confirmação. |

| **Resultado da execução** |
| :------------------------ |
| **A executar.**           |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
