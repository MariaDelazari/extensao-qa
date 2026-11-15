## Cenário 33: Modelos e categorias de anamnese na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de categorias de anamnese.

| ID       | Descrição                                                                                              |
| :------- | :----------------------------------------------------------------------------------------------------- |
| C33-CT01 | Verificar se a tela de categorias de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                                                 |
| **QUANDO** clicarmos em "Categorias" no grupo Saúde do menu lateral                                                                                                                                                        |
| **ENTÃO** a tela "Categorias de Anamnese" deverá abrir com a busca "Buscar categoria...", o filtro de status, o botão "Nova Categoria", os indicadores Total, Ativas, Inativas e Com perguntas e as categorias cadastradas |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A tela de categorias abre pelo menu com todos os seus componentes. |

| **Resultado da execução**                                                                                                                                                                                         |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A tela abriu em `/anamnese/categorias` com a busca, o filtro "Todos os status", o botão "Nova Categoria", os indicadores (Total 3, Ativas 3, Inativas 0, Com perguntas 3) e as categorias em cartões. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Salvar categoria com o formulário vazio.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C33-CT02 | Verificar se o sistema impede o cadastro de categoria sem nome. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Categoria"                                         |
| **E** deixamos o campo "Nome da Categoria" vazio                                  |
| **QUANDO** tentarmos clicar em "Criar Categoria"                                  |
| **ENTÃO** o botão deverá ficar desabilitado e nenhuma categoria deverá ser criada |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| A categoria não é salva sem nome e o campo aparece como obrigatório. |

| **Resultado da execução**                                                                                                                                                      |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O campo "Nome da Categoria" tem o asterisco de obrigatório e o botão "Criar Categoria" fica desabilitado enquanto o nome está vazio; nenhuma requisição é enviada. |

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
| **E** informamos o nome "Categoria Teste Maria", o ícone "bi-heart", a cor "#dc2626" e o status Ativo   |
| **QUANDO** clicarmos no botão "Criar Categoria"                                                         |
| **ENTÃO** a categoria deverá aparecer na listagem e os indicadores Total e Ativas deverão aumentar em 1 |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A categoria é salva com os dados informados e aparece na listagem. |

| **Resultado da execução**                                                                                                          |
| :--------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A categoria apareceu na listagem com o ícone e a cor escolhidos, e os indicadores Total e Ativas passaram de 3 para 4. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Indicador "Com perguntas" das categorias.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C33-CT04 | Verificar se o indicador "Com perguntas" conta só as categorias que têm perguntas. |

| **Pré-condições**                                                                                            |
| :----------------------------------------------------------------------------------------------------------- |
| Ter acabado de cadastrar a categoria "Categoria Teste Maria" (C33-CT03), que ainda não tem nenhuma pergunta. |

| **Passos**                                                                          |
| :---------------------------------------------------------------------------------- |
| **DADO** que anotamos o indicador "Com perguntas" antes do cadastro (3)             |
| **QUANDO** cadastrarmos a categoria "Categoria Teste Maria", sem pergunta vinculada |
| **ENTÃO** o indicador "Com perguntas" deverá continuar em 3                         |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O indicador "Com perguntas" não muda ao cadastrar uma categoria sem perguntas. |

| **Resultado da execução**                                                                                                                                         |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O indicador "Com perguntas" passou de 3 para 4 junto com o Total. Ele mostra a quantidade total de categorias, e não as categorias que têm perguntas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Cadastro de categoria duplicada.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C33-CT05 | Verificar se o sistema impede cadastrar duas categorias com o mesmo nome. |

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

| **Resultado da execução**                                                                                                                                         |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A segunda "Categoria Teste Maria" foi salva sem nenhum aviso (resposta 201) e a listagem passou a mostrar duas categorias com o mesmo nome (Total 5). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Busca de categoria pelo nome.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C33-CT06 | Verificar se a busca filtra as categorias pelo nome. |

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

| **Resultado da execução**                                                                                                                      |
| :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Com "Teste Maria" na busca, a listagem mostrou só as categorias "Categoria Teste Maria"; os indicadores continuaram com os totais. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Alteração de categoria.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT07 | Verificar se a categoria pode ser alterada e inativada. |

| **Pré-condições**                            |
| :------------------------------------------- |
| Existir a categoria "Categoria Teste Maria". |

| **Passos**                                                                                                     |
| :------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no botão "Editar" do cartão "Categoria Teste Maria"                                      |
| **E** alteramos o status para Inativo na janela "Editar Categoria"                                             |
| **QUANDO** clicarmos no botão "Atualizar"                                                                      |
| **ENTÃO** a categoria deverá aparecer como Inativo, e os indicadores Ativas e Inativas deverão ser atualizados |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A alteração é salva e aparece na listagem e nos indicadores. |

| **Resultado da execução**                                                                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A janela "Editar Categoria" abriu com os dados da categoria; ao clicar em "Atualizar", ela passou a Inativo, Ativas foi de 5 para 4 e Inativas de 0 para 1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Exclusão de categoria.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C33-CT08 | Verificar se a categoria é excluída ao confirmar a exclusão. |

| **Pré-condições**                            |
| :------------------------------------------- |
| Existir a categoria "Categoria Teste Maria". |

| **Passos**                                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no botão "Excluir" do cartão "Categoria Teste Maria"                             |
| **QUANDO** confirmarmos a mensagem "Excluir a categoria "Categoria Teste Maria"?" no botão "Confirmar" |
| **ENTÃO** a categoria deverá sair da listagem e o indicador Total deverá diminuir em 1                 |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| A categoria é excluída somente após a confirmação. |

| **Resultado da execução**                                                                                                                                                                    |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Apareceu a mensagem "Excluir a categoria "Categoria Teste Maria"?" com os botões "Cancelar" e "Confirmar"; ao confirmar, a categoria saiu da listagem e o Total foi de 5 para 4. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Acesso à tela de modelos de anamnese.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C33-CT09 | Verificar se a tela de modelos de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                                                       |
| **QUANDO** clicarmos em "Modelos" no grupo Saúde do menu lateral                                                                                                                                                                 |
| **ENTÃO** a tela "Modelos de Anamnese" deverá abrir com a busca "Buscar modelo...", o filtro de status, o botão "Novo Modelo", os indicadores Total de modelos, Ativos, Média de perguntas e Aplicações e os modelos cadastrados |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| A tela de modelos abre pelo menu com todos os seus componentes. |

| **Resultado da execução**                                                                                                                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A tela abriu em `/anamnese/modelos` com a busca, o filtro de status, o botão "Novo Modelo", os indicadores (Total de modelos 3, Ativos 2, Média de perguntas 1, Aplicações 15) e os cartões dos modelos com os botões "Editar" e "Preview". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Salvar modelo sem nome.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C33-CT10 | Verificar se o sistema impede o cadastro de modelo sem nome. |

| **Pré-condições**                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Modelos de Anamnese" está aberta. |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo"                                        |
| **E** deixamos o campo "Nome do Modelo" vazio                                 |
| **QUANDO** tentarmos clicar em "Salvar Modelo"                                |
| **ENTÃO** o botão deverá ficar desabilitado e nenhum modelo deverá ser criado |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O modelo não é salvo sem nome e o campo aparece como obrigatório. |

| **Resultado da execução**                                                                                                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** "Novo Modelo" abriu a página "Novo Modelo de Anamnese" (`/anamnese/modelos/novo`); com o nome vazio, o botão "Salvar Modelo" fica desabilitado e o campo "Nome do Modelo" tem o asterisco de obrigatório. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Cadastro de modelo com pergunta.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT11 | Verificar se o modelo é salvo com a pergunta escolhida. |

| **Pré-condições**                                                 |
| :---------------------------------------------------------------- |
| Existir a pergunta "Manual SIFIT Lesão" em Perguntas de anamnese. |

| **Passos**                                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo"                                                                             |
| **E** informamos o nome "Modelo Teste Maria" e a descrição "Modelo criado no teste do cenário 33"                  |
| **E** clicamos no "+" da pergunta "Manual SIFIT Lesão" e marcamos "Obrigatória"                                    |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                                      |
| **ENTÃO** o modelo deverá aparecer na listagem com 1 pergunta, e o indicador Total de modelos deverá aumentar em 1 |

| **Critérios de aceitação**                                                |
| :------------------------------------------------------------------------ |
| O modelo é salvo com a pergunta escolhida e a listagem mostra 1 pergunta. |

| **Resultado da execução**                                                                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A pergunta foi para "Modelo atual" e o "Resumo do Modelo" mostrou 1 pergunta e 1 obrigatória; ao salvar, o modelo apareceu na listagem com "1 perguntas" e o Total de modelos passou de 3 para 4. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 12: Pergunta obrigatória na edição do modelo.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C33-CT12 | Verificar se a edição do modelo mostra a pergunta marcada como obrigatória. |

| **Pré-condições**                                                                                              |
| :------------------------------------------------------------------------------------------------------------- |
| Existir o modelo "Modelo Teste Maria" com a pergunta "Manual SIFIT Lesão" marcada como obrigatória (C33-CT11). |

| **Passos**                                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Modelos de Anamnese"                                                                          |
| **QUANDO** clicarmos em "Editar" no modelo "Modelo Teste Maria"                                                             |
| **ENTÃO** a pergunta "Manual SIFIT Lesão" deverá aparecer com "Obrigatória" marcada e o resumo deverá mostrar 1 obrigatória |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| A edição mostra a marcação de obrigatória que foi salva. |

| **Resultado da execução**                                                                                                                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A página "Editar Modelo" abriu com "Obrigatória" desmarcada (Obrigatórias 0, Opcionais 1), embora a API devolva a pergunta com "obrigatoria": "1". Ao salvar a edição sem marcar de novo, a marcação é apagada. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 13: Preview do modelo "Triplet".

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C33-CT13 | Verificar se o preview mostra as perguntas que o card do modelo informa. |

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

| **Resultado da execução**                                                                                                                                                                                                                                                |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A janela mostrou o nome e a descrição "Triplet" e a mensagem "Nenhuma pergunta adicionada ainda.", embora o card informe "1 perguntas". O preview de "Manual SIFIT Anamnese Inicial" e o de "Modelo Teste Maria", que têm 1 pergunta, também ficaram vazios. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 14: Alteração de modelo.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C33-CT14 | Verificar se o modelo pode ser alterado e inativado. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| Existir o modelo "Modelo Teste Maria", cadastrado no C33-CT11. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Editar" no modelo "Modelo Teste Maria"                                                  |
| **E** alteramos a descrição para "Modelo alterado no teste do cenário 33" e o status para Inativo                 |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                                     |
| **ENTÃO** o modelo deverá aparecer como Inativo e com a nova descrição, e o indicador Ativos deverá diminuir em 1 |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A alteração é salva e aparece na listagem e nos indicadores. |

| **Resultado da execução**                                                                                                                                    |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O modelo voltou para a listagem como Inativo, com a descrição "Modelo alterado no teste do cenário 33", e o indicador Ativos passou de 3 para 2. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 15: Exclusão de modelo.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C33-CT15 | Verificar se o modelo é excluído ao confirmar a exclusão. |

| **Pré-condições**                      |
| :------------------------------------- |
| Existir o modelo "Modelo Teste Maria". |

| **Passos**                                                                                       |
| :----------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no ícone de lixeira do modelo "Modelo Teste Maria"                         |
| **QUANDO** confirmarmos a mensagem "Excluir o modelo "Modelo Teste Maria"?" no botão "Confirmar" |
| **ENTÃO** o modelo deverá sair da listagem e o indicador Total de modelos deverá diminuir em 1   |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O modelo é excluído somente após a confirmação. |

| **Resultado da execução**                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** Apareceu a mensagem "Excluir o modelo "Modelo Teste Maria"?"; ao confirmar, o modelo saiu da listagem e o Total de modelos foi de 4 para 3. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
