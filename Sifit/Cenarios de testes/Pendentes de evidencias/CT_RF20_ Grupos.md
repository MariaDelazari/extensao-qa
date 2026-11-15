## Cenário 20: Grupos na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de grupos.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C20-CT01 | Verificar se a tela de grupos é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos autenticados no SIFIT                                                                                                                          |
| **QUANDO** acessarmos o menu "Grupos"                                                                                                                               |
| **ENTÃO** a tela deverá exibir os filtros (Código, Nome, Status e Tipo Caixa), os indicadores (Grupos, Ativos, Mostrar Home e Caixa Externo) e a listagem de grupos |

| **Critérios de aceitação**                                                       |
| :------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de grupos com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Busca de grupo pelo nome.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C20-CT02 | Verificar se a busca pelo nome retorna os grupos correspondentes. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existirem grupos com "Treino" no nome. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos                                    |
| **E** informamos "treino" no campo "Nome"                                 |
| **QUANDO** clicarmos no botão de busca                                    |
| **ENTÃO** a listagem deverá exibir somente os grupos com "Treino" no nome |

| **Critérios de aceitação**                                                                  |
| :------------------------------------------------------------------------------------------ |
| O sistema deve filtrar os grupos pelo nome, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                 |
| :------------------------------------------------------------------------ |
| **Passou.** A listagem exibiu somente "Treino Livre" e "Treino Personal". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Busca de grupo com código inexistente.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C20-CT03 | Verificar se o sistema informa que nenhum grupo foi encontrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos                              |
| **E** informamos "999" no campo "Código"                            |
| **QUANDO** clicarmos no botão de busca                              |
| **ENTÃO** o sistema deverá informar que nenhum grupo foi encontrado |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa quando a busca não retornar resultados. |

| **Resultado da execução**                                              |
| :--------------------------------------------------------------------- |
| **Passou.** A tela exibiu "Nenhum grupo encontrado" e "0 registro(s)". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastro de grupo sem nome.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C20-CT04 | Verificar se o sistema impede o cadastro de grupo sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Novo Grupo"                                            |
| **E** mantemos o campo "Nome" vazio                                                   |
| **QUANDO** clicarmos no botão "Salvar Grupo"                                          |
| **ENTÃO** o sistema deverá solicitar o preenchimento do nome ("Preencha este campo.") |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o nome seja informado. |

| **Resultado da execução**                                                                  |
| :----------------------------------------------------------------------------------------- |
| **Passou.** O campo "Nome" mostrou o aviso "Preencha este campo." e o grupo não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Cadastro de grupo com dados válidos.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C20-CT05 | Verificar se o grupo é cadastrado e os indicadores são atualizados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                               |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Novo Grupo"                                                                                               |
| **E** informamos o nome "Grupo Teste Ville", Mostrar Home "Sim", Tipo Caixa "Externo" e a descrição "Grupo de teste do Ville"            |
| **QUANDO** clicarmos no botão "Salvar Grupo"                                                                                             |
| **ENTÃO** o grupo deverá constar na listagem e os indicadores "Grupos", "Ativos", "Mostrar Home" e "Caixa Externo" deverão aumentar em 1 |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve cadastrar o grupo e atualizar os indicadores. |

| **Resultado da execução**                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** O grupo "Grupo Teste Ville" foi listado como ATIVO e os indicadores passaram de 6, 6, 4 e 0 para 7, 7, 5 e 1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Filtro de grupos por tipo de caixa.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C20-CT06 | Verificar se o filtro "Tipo Caixa" exibe somente os grupos do tipo selecionado. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo "Grupo Teste Ville" com Tipo Caixa "Externo". |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos                              |
| **E** selecionamos "Externo" no filtro "Tipo Caixa"                 |
| **QUANDO** clicarmos no botão de busca                              |
| **ENTÃO** a listagem deverá exibir somente grupos do tipo "Externo" |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve filtrar os grupos pelo tipo de caixa selecionado. |

| **Resultado da execução**                                          |
| :----------------------------------------------------------------- |
| **Passou.** A listagem exibiu somente os grupos do tipo "Externo". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Cadastro de grupo duplicado.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C20-CT07 | Verificar se o sistema impede o cadastro de grupo com nome já existente. |

| **Pré-condições**                                                       |
| :---------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo "Grupo Teste Ville". |

| **Passos**                                                    |
| :------------------------------------------------------------ |
| **DADO** que o grupo "Grupo Teste Ville" já está cadastrado   |
| **E** abrimos a janela "Novo Grupo" e informamos o mesmo nome |
| **QUANDO** clicarmos no botão "Salvar Grupo"                  |
| **ENTÃO** o sistema deverá informar que o grupo já existe     |

| **Critérios de aceitação**                           |
| :--------------------------------------------------- |
| O sistema não deve permitir grupos com o mesmo nome. |

| **Resultado da execução**                                                                    |
| :------------------------------------------------------------------------------------------- |
| **Falhou.** O grupo foi cadastrado de novo (códigos #8 e #9 com o nome "Grupo Teste Ville"). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Alteração de grupo.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C20-CT08 | Verificar se os dados do grupo podem ser alterados. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo de teste #9. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que clicamos no botão de visualizar do grupo #9                          |
| **E** alteramos o nome para "Grupo Teste Ville Editado" e Mostrar Home para "Não" |
| **QUANDO** clicarmos no botão "Salvar Grupo"                                      |
| **ENTÃO** a listagem deverá exibir o nome e o Mostrar Home atualizados            |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| O sistema deve salvar as alterações do grupo. |

| **Resultado da execução**                                                                  |
| :----------------------------------------------------------------------------------------- |
| **Passou.** A listagem passou a exibir "Grupo Teste Ville Editado" com Mostrar Home "Nao". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Inativação de grupo.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C20-CT09 | Verificar se o grupo pode ser cadastrado ou alterado com o status "Inativo". |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo de teste #9. |

| **Passos**                                                                                  |
| :------------------------------------------------------------------------------------------ |
| **DADO** que clicamos no botão de visualizar do grupo #9                                    |
| **E** selecionamos "Inativo" no campo "Status"                                              |
| **QUANDO** clicarmos no botão "Salvar Grupo"                                                |
| **ENTÃO** o grupo deverá constar como "INATIVO" e o indicador "Ativos" deverá diminuir em 1 |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| O sistema deve salvar o status do grupo e atualizar os indicadores. |

| **Resultado da execução**                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O grupo continua "ATIVO" e o indicador "Ativos" não muda. O mesmo ocorre ao cadastrar um grupo novo como "Inativo" ("Grupo Inativo Ville"). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Exclusão de grupo.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C20-CT10 | Verificar se o grupo é excluído ao confirmar a exclusão. |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo de teste #10. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de grupos                                |
| **E** clicamos no botão de excluir do grupo #10 "Grupo Inativo Ville" |
| **QUANDO** confirmarmos a mensagem "Deseja deletar o Grupo?"          |
| **ENTÃO** o grupo não deverá mais constar na listagem                 |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema deve solicitar confirmação e excluir o grupo. |

| **Resultado da execução**                                                                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A confirmação fecha sem nenhuma mensagem e o grupo continua na listagem. No DevTools (aba Network), a exclusão retorna erro 500 "Erro interno inesperado.". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
