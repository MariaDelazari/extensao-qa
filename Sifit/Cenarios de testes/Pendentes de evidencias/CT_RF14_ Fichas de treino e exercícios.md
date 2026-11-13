## Cenário 14: Fichas de treino e exercícios na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de fichas de treino.

| ID       | Descrição                                                                                      |
| :------- | :--------------------------------------------------------------------------------------------- |
| C14-CT01 | Verificar se a tela de fichas de treino é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                     |
| **QUANDO** acessarmos o menu "Ficha de Treino"                                                                                                                 |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Fichas cadastradas, Fichas ativas, Vencendo em 7 dias e Vencidas/canceladas) e a listagem de fichas |

| **Critérios de aceitação**                                                                 |
| :----------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de fichas de treino com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Cadastro de ficha sem aluno.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C14-CT02 | Verificar se o sistema impede a criação da ficha sem aluno. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Cadastrar Ficha"                     |
| **E** não selecionamos nenhum aluno                                 |
| **QUANDO** clicarmos no botão "Criar Nova Ficha"                    |
| **ENTÃO** o sistema deverá apresentar o aviso "Selecione um aluno." |

| **Critérios de aceitação**                                                   |
| :--------------------------------------------------------------------------- |
| O sistema deve impedir a criação da ficha até que um aluno seja selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Cadastro de ficha sem objetivo.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C14-CT03 | Verificar se o sistema informa que o objetivo do treino é obrigatório. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Cadastrar Ficha"                     |
| **E** selecionamos o aluno "Steven Kaiki" e o personal "Santhago"   |
| **E** não selecionamos o objetivo do treino                         |
| **QUANDO** clicarmos no botão "Criar Nova Ficha"                    |
| **ENTÃO** o sistema deverá informar "Escolha o objetivo do treino." |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O sistema deve informar ao usuário o campo obrigatório que não foi preenchido. |

| **Resultado da execução**                            |
| :--------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro ao salvar Ficha.". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastro de ficha com dados válidos.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C14-CT04 | Verificar se a ficha é criada ao informar os dados corretamente. |

| **Pré-condições**                                                                                       |
| :------------------------------------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir objetivo de treino cadastrado (ex.: "Objetivo Teste Ville"). |

| **Passos**                                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Cadastrar Ficha"                                                                             |
| **E** selecionamos o aluno "Steven Kaiki", o personal "Santhago" e o objetivo "Objetivo Teste Ville"                        |
| **QUANDO** clicarmos no botão "Criar Nova Ficha"                                                                            |
| **ENTÃO** deveremos ser direcionados à tela de montagem dos treinos e a ficha deverá constar na listagem com status "ATIVO" |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve criar a ficha e permitir a montagem dos treinos. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Montagem e salvamento dos treinos da ficha.

| ID       | Descrição                                    |
| :------- | :------------------------------------------- |
| C14-CT05 | Verificar se os treinos da ficha são salvos. |

| **Pré-condições**                                        |
| :------------------------------------------------------- |
| O usuário deve estar autenticado e existir ficha criada. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que estamos na tela de montagem dos treinos da ficha             |
| **E** clicamos em "Adicionar Treino" (Treino A)                           |
| **QUANDO** clicarmos no botão "Salvar Ficha"                              |
| **ENTÃO** o sistema deverá salvar os treinos e exibir mensagem de sucesso |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| O sistema deve salvar os treinos da ficha. |

| **Resultado da execução**                                                         |
| :-------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro no servidor" ao salvar e ao visualizar a ficha. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Visualização da ficha de treino.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C14-CT06 | Verificar se a ficha cadastrada pode ser aberta pela listagem. |

| **Pré-condições**                                            |
| :----------------------------------------------------------- |
| O usuário deve estar autenticado e existir ficha cadastrada. |

| **Passos**                                                                          |
| :---------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de fichas de treino                                    |
| **QUANDO** clicarmos no botão "Visualizar" da ficha de Steven Kaiki                 |
| **ENTÃO** a ficha deverá ser aberta com seus dados e treinos, sem mensagens de erro |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| O sistema deve exibir a ficha selecionada. |

| **Resultado da execução**                                                         |
| :-------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro no servidor" ao salvar e ao visualizar a ficha. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Exclusão de ficha de treino.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C14-CT07 | Verificar se a ficha é excluída ao confirmar a exclusão. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir ficha de teste cadastrada. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos na tela de fichas de treino                |
| **E** clicamos no botão "Deletar" da ficha de Steven Kaiki      |
| **QUANDO** confirmarmos a mensagem "Deseja deletar esta ficha?" |
| **ENTÃO** a ficha não deverá mais constar na listagem           |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema deve solicitar confirmação e excluir a ficha. |

| **Resultado da execução**                                                                            |
| :--------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao excluir a ficha, o DevTools (aba Network) mostra comandos SQL na resposta do sistema. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Acesso à biblioteca de exercícios.

| ID       | Descrição                                                                           |
| :------- | :---------------------------------------------------------------------------------- |
| C14-CT08 | Verificar se a tela de exercícios exibe os exercícios agrupados por grupo muscular. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                            |
| **QUANDO** acessarmos o menu "Exercícios"                                                                             |
| **ENTÃO** a tela deverá exibir o total de exercícios e os grupos musculares com seus exercícios e o botão "Adicionar" |

| **Critérios de aceitação**                        |
| :------------------------------------------------ |
| O sistema deve exibir a biblioteca de exercícios. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Salvar Exercícios com o formulário vazio.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C14-CT09 | O cadastro de Exercícios não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Adicionar" em `/exercicios`                     |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Exibido o aviso "Informe o nome do exercício.". Em 28/10/2026, no Sifit Unialfa, o caso passou: apareceu o aviso "Informe o nome do exercicio." e o cadastro não foi salvo. |

| **Evidência(s)**                    |
| :---------------------------------- |
| [Print](../../Evidencias/C14-CT09.png) |

---

### Caso de Teste 10: Cadastro de exercício com dados válidos.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C14-CT10 | Verificar se o exercício é cadastrado no grupo muscular selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                            |
| :---------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Adicionar" no grupo "Peitoral"                                              |
| **E** informamos o nome "Exercício Teste Ville"                                                       |
| **QUANDO** clicarmos no botão "Salvar"                                                                |
| **ENTÃO** o exercício deverá constar no grupo "Peitoral" e o total de exercícios deverá aumentar em 1 |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve cadastrar o exercício e atualizar o total. |

| **Resultado da execução**                                     |
| :------------------------------------------------------------ |
| **Passou.** Exercício listado em Peitoral e total atualizado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/35d0b2b5-9ac2-4c7a-a63f-a172aeaaa7dc) |

---

### Caso de Teste 11: Cadastro de exercício duplicado.

| ID       | Descrição                                                                                   |
| :------- | :------------------------------------------------------------------------------------------ |
| C14-CT11 | Verificar se o sistema impede o cadastro de exercício com nome já existente no mesmo grupo. |

| **Pré-condições**                                                                                   |
| :-------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o exercício "Exercício Teste Ville" no grupo "Peitoral". |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que o exercício "Exercício Teste Ville" já existe no grupo "Peitoral" |
| **E** clicamos em "Adicionar" no grupo "Peitoral" e informamos o mesmo nome    |
| **QUANDO** clicarmos no botão "Salvar"                                         |
| **ENTÃO** o sistema deverá informar que o exercício já está cadastrado         |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema não deve permitir exercícios duplicados no mesmo grupo. |

| **Resultado da execução**                                                         |
| :-------------------------------------------------------------------------------- |
| **Falhou.** O exercício duplicado foi salvo; o grupo passou a ter 2 itens iguais. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a84d54b0-8ca9-4871-9a16-5c563024a8f4) |

---

### Caso de Teste 12: Alteração de exercício.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C14-CT12 | Verificar se o nome do exercício pode ser alterado. |

| **Pré-condições**                                                               |
| :------------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir o exercício "Exercício Teste Ville". |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que clicamos em "Visualizar" do exercício "Exercício Teste Ville" |
| **E** alteramos o nome para "Exercício Teste Ville Editado"                |
| **QUANDO** clicarmos no botão "Salvar"                                     |
| **ENTÃO** o exercício deverá ser exibido com o novo nome                   |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O sistema deve salvar a alteração do exercício. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 13: Exclusão de exercício.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C14-CT13 | Verificar se o exercício é excluído ao confirmar a exclusão. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir exercício de teste cadastrado. |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de exercícios                                       |
| **E** clicamos no botão "Deletar" do exercício "Exercício Teste Ville Editado"   |
| **QUANDO** confirmarmos a mensagem "Deseja deletar o Exercício?"                 |
| **ENTÃO** o exercício não deverá mais constar e o total deverá ser reduzido em 1 |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O sistema deve solicitar confirmação e excluir o exercício. |

| **Resultado da execução**                          |
| :------------------------------------------------- |
| **Passou.** Exercício removido e total atualizado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/77fa5e4f-a14b-41ce-9c31-e1515abaecc1) |
