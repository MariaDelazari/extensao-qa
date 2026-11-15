## Cenário 23: Grupos musculares na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de grupos musculares.

| ID       | Descrição                                                                                       |
| :------- | :---------------------------------------------------------------------------------------------- |
| C23-CT01 | Verificar se a tela de grupos musculares é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                           |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                           |
| **QUANDO** acessarmos o menu "Grupos Musculares"                                                                                                                     |
| **ENTÃO** a tela deverá exibir os filtros (Código, Nome e Tipo Membro), os indicadores (Grupos cadastrados, Superiores, Inferiores e Aerobio) e a listagem de grupos |

| **Critérios de aceitação**                                                                  |
| :------------------------------------------------------------------------------------------ |
| O sistema deve exibir a tela de grupos musculares com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/7b8f2086-48da-49a7-ae49-1cd24456d0b0) |

---

### Caso de Teste 02: Busca de grupo muscular pelo nome.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C23-CT02 | Verificar se a busca pelo nome retorna os grupos correspondentes. |

| **Pré-condições**                                                        |
| :----------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem grupos com "Teste" no nome. |

| **Passos**                                                               |
| :----------------------------------------------------------------------- |
| **DADO** que estamos na tela de grupos musculares                        |
| **E** informamos "teste" no campo "Nome"                                 |
| **QUANDO** clicarmos no botão "Buscar"                                   |
| **ENTÃO** a listagem deverá exibir somente os grupos com "Teste" no nome |

| **Critérios de aceitação**                                                                  |
| :------------------------------------------------------------------------------------------ |
| O sistema deve filtrar os grupos pelo nome, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                                         |
| :------------------------------------------------------------------------------------------------ |
| **Passou.** A listagem exibiu somente os grupos com "teste" no nome, em maiúsculas ou minúsculas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/74916f35-5d48-454b-8619-826584ba2f9c) |

---

### Caso de Teste 03: Busca de grupo muscular com código inexistente.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C23-CT03 | Verificar se o sistema informa que nenhum grupo foi encontrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos musculares                   |
| **E** informamos "999" no campo "Código"                            |
| **QUANDO** clicarmos no botão "Buscar"                              |
| **ENTÃO** o sistema deverá informar que nenhum grupo foi encontrado |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa quando a busca não retornar resultados. |

| **Resultado da execução**                                                                     |
| :-------------------------------------------------------------------------------------------- |
| **Passou.** A tela exibiu "Nenhum grupo muscular encontrado" e "Mostrando 0 a 0 de 0 grupos". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/6ebe6a2e-6c51-4736-8476-8fcbe56f6845) |

---

### Caso de Teste 04: Filtro de grupos musculares por tipo de membro.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C23-CT04 | Verificar se o filtro "Tipo Membro" lista somente os grupos do tipo escolhido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                              |
| :------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos musculares                                                       |
| **E** selecionamos "Aerobio" no filtro "Tipo Membro"                                                    |
| **QUANDO** clicarmos no botão "Buscar"                                                                  |
| **ENTÃO** a listagem deverá exibir somente grupos "Aerobio", na mesma quantidade do indicador "Aerobio" |

| **Critérios de aceitação**                                                                   |
| :------------------------------------------------------------------------------------------- |
| O filtro deve listar somente o tipo escolhido, e a quantidade deve ser igual à do indicador. |

| **Resultado da execução**                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A listagem exibiu somente grupos "Aerobio", na mesma quantidade do indicador. O filtro "Superiores" também bateu com o indicador. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/d3df52b8-feaf-4066-a988-6f1850a7ef19) |

---

### Caso de Teste 05: Limpar filtros.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C23-CT05 | Verificar se o botão "Limpar filtros" apaga os filtros e volta a listar todos os grupos. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que aplicamos filtros de nome e de tipo de membro                                    |
| **QUANDO** clicarmos no botão "Limpar filtros"                                                |
| **ENTÃO** os campos de filtro deverão ficar vazios e a listagem deverá exibir todos os grupos |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema deve voltar à listagem completa, sem filtros. |

| **Resultado da execução**                                                           |
| :---------------------------------------------------------------------------------- |
| **Passou.** Os filtros foram apagados e a listagem voltou a exibir todos os grupos. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/d9b13459-c818-46c1-97e0-75acd067f8ed) |

---

### Caso de Teste 06: Paginação da listagem de grupos musculares.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C23-CT06 | Verificar se a troca de página e da quantidade por página funcionam. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem mais de 10 grupos. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de grupos musculares com "10 por pagina"                                      |
| **QUANDO** clicarmos na página "2" e depois escolhermos "20 por pagina"                                    |
| **ENTÃO** a página 2 deverá exibir os grupos seguintes e "20 por pagina" deverá exibir todos em uma página |

| **Critérios de aceitação**                                                                 |
| :----------------------------------------------------------------------------------------- |
| O rodapé "Mostrando X a Y de Z grupos" deve acompanhar a página e a quantidade escolhidas. |

| **Resultado da execução**                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A página 2 exibiu os grupos seguintes e "20 por pagina" exibiu todos em uma página, com o rodapé correto. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/cfcffad0-0b7b-4d44-97e1-4f392ebcb34d) |

---

### Caso de Teste 07: Salvar Grupos Musculares com o formulário vazio.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C23-CT07 | Verificar se o sistema indica os campos obrigatórios ao salvar o formulário vazio. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Grupo Muscular" pelo botão "Cadastrar grupo"      |
| **E** deixamos todos os campos vazios                                            |
| **QUANDO** clicarmos no botão "Salvar"                                           |
| **ENTÃO** o sistema deverá indicar os campos obrigatórios e não criar o registro |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve indicar quais campos faltam e não salvar o grupo. |

| **Resultado da execução**                                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tela mostrou só "Erro ao salvar grupo", sem indicar o campo que falta. No DevTools, o servidor responde com erro 500. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/f15db91c-a5d3-44f0-b1f0-db64a1f71324) |

---

### Caso de Teste 08: Cadastro de grupo muscular sem tipo de membro.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C23-CT08 | Verificar se o sistema indica que o tipo de membro é obrigatório. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Grupo Muscular"                                   |
| **E** informamos o nome "Grupo Teste Keltton" e não selecionamos o "Tipo Membro" |
| **QUANDO** clicarmos no botão "Salvar"                                           |
| **ENTÃO** o sistema deverá informar que o "Tipo Membro" é obrigatório            |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve indicar o campo que falta, com uma mensagem clara. |

| **Resultado da execução**                                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tela mostrou só "Erro ao salvar grupo". O campo "Tipo Membro" não tem a opção "Selecione" nem a marca de obrigatório. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/0d60d44e-1515-473a-9bec-0256ac5b11ee) |

---

### Caso de Teste 09: Cadastro de grupo muscular sem nome.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C23-CT09 | Verificar se o sistema impede o cadastro de grupo sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Grupo Muscular"                                   |
| **E** mantemos o campo "Nome" vazio e selecionamos "Inferiores" em "Tipo Membro" |
| **QUANDO** clicarmos no botão "Salvar"                                           |
| **ENTÃO** o sistema deverá solicitar o preenchimento do nome                     |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o nome seja informado. |

| **Resultado da execução**                                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O grupo foi salvo sem nome: apareceu na listagem com o nome em branco e o indicador "Grupos cadastrados" aumentou em 1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/c795c2dd-5974-4a61-95d1-c4d3fc0734f5) |

---

### Caso de Teste 10: Cadastro de grupo muscular com dados válidos.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C23-CT10 | Verificar se o grupo é cadastrado e os indicadores são atualizados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                              |
| :---------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Grupo Muscular"                                                                          |
| **E** informamos o nome "Teste" e selecionamos "Superiores" em "Tipo Membro"                              |
| **QUANDO** clicarmos no botão "Salvar"                                                                                  |
| **ENTÃO** o grupo deverá constar na listagem e os indicadores "Grupos cadastrados" e "Superiores" deverão aumentar em 1 |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O grupo deve ser salvo e os indicadores devem ser atualizados. |

| **Resultado da execução**                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O grupo "Teste" apareceu na listagem como "Superiores" e os dois indicadores aumentaram em 1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/60718def-2be2-4683-af14-d250077db522) |

---

### Caso de Teste 11: Cadastro de grupo muscular duplicado.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C23-CT11 | Verificar se o sistema impede dois grupos com o mesmo nome. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir o grupo "Grupo Teste Keltton". |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que o grupo "Teste" já está cadastrado                    |
| **E** abrimos a janela "Grupo Muscular" e informamos o mesmo nome e o mesmo tipo |
| **QUANDO** clicarmos no botão "Salvar"                                           |
| **ENTÃO** o sistema deverá informar que o grupo já existe                        |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema não deve permitir grupos musculares com o mesmo nome. |

| **Resultado da execução**                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O grupo foi cadastrado de novo. A listagem passou a ter dois "Grupo Teste Keltton" com códigos diferentes. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/413c4e06-4999-4b2e-b9f6-8e13ae2a7e46) |

---

### Caso de Teste 12: Alteração de grupo muscular.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C23-CT12 | Verificar se o nome e o tipo de membro do grupo podem ser alterados. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir o grupo "Grupo Teste Keltton". |

| **Passos**                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no botão "Visualizar" do grupo "Teste"                                                 |
| **E** alteramos o nome para "Keltton" e o "Tipo Membro" para "Inferiores"                              |
| **QUANDO** clicarmos no botão "Salvar"                                                                                     |
| **ENTÃO** a listagem deverá exibir o nome e o tipo atualizados, e os indicadores "Superiores" e "Inferiores" deverão mudar |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| As alterações devem ser salvas e refletidas na listagem e nos indicadores. |

| **Resultado da execução**                                                                                                          |
| :--------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A listagem exibiu "Keltton" como "Inferiores"; "Superiores" diminuiu e "Inferiores" aumentou em 1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/018f87df-85f1-4eb3-bccf-80b672c3c85c) |

---

### Caso de Teste 13: Exclusão de grupo muscular.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C23-CT13 | Verificar se o grupo é excluído após a confirmação. |

| **Pré-condições**                                                            |
| :--------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir um grupo de teste sem exercícios. |

| **Passos**                                                                                                    |
| :------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de grupos musculares                                                             |
| **E** clicamos no botão "Deletar" do grupo de teste                                                           |
| **QUANDO** confirmarmos a mensagem "Deseja deletar o Grupo?"                                                  |
| **ENTÃO** o grupo não deverá mais constar na listagem e o indicador "Grupos cadastrados" deverá diminuir em 1 |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O grupo deve ser excluído e os indicadores devem ser atualizados. |

| **Resultado da execução**                                                |
| :----------------------------------------------------------------------- |
| **Passou.** O grupo saiu da listagem e os indicadores foram atualizados. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/f812432a-814f-417d-9e88-f6f69c4a4422) |

---

### Caso de Teste 14: Grupo muscular novo na biblioteca de exercícios.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C23-CT14 | Verificar se o grupo cadastrado aparece na tela de Exercícios e aceita exercícios. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o grupo "Keltton". |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que cadastramos o grupo "Keltton"                        |
| **QUANDO** acessarmos o menu "Exercícios" e clicarmos em "Adicionar" no card do grupo |
| **E** salvarmos o exercício "Teste Keltton"                                 |
| **ENTÃO** o exercício deverá constar no card do grupo                                 |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O grupo novo deve estar disponível na biblioteca de exercícios. |

| **Resultado da execução**                                                                                            |
| :------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O card "Keltton" apareceu em Exercícios e passou a listar "Teste Keltton". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/726c0ef8-7c8c-4d8f-b39e-fb9e2228b28c) |

---

### Caso de Teste 15: Exclusão de grupo muscular com exercício vinculado.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C23-CT15 | Verificar se o sistema impede a exclusão de grupo com exercícios e explica o motivo. |

| **Pré-condições**                                                                     |
| :------------------------------------------------------------------------------------ |
| O grupo "Grupo Teste Keltton Editado" deve ter o exercício "Exercicio Teste Keltton". |

| **Passos**                                                                             |
| :------------------------------------------------------------------------------------- |
| **DADO** que o grupo de teste tem um exercício vinculado                               |
| **E** clicamos no botão "Deletar" do grupo                                             |
| **QUANDO** confirmarmos a mensagem "Deseja deletar o Grupo?"                           |
| **ENTÃO** o sistema deverá impedir a exclusão e informar que o grupo possui exercícios |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| A exclusão deve ser bloqueada com uma mensagem que explique o motivo. |

| **Resultado da execução**                                                                                                                                                                        |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A exclusão foi bloqueada e o grupo continuou na listagem, mas a tela mostrou só "Erro ao deletar Grupo". No DevTools, o servidor responde com erro 500 e "Erro interno inesperado.". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/03438160-a0a6-4bce-b9b6-2c79b0d3a692) |

---
