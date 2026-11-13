## Cenário 10: Avaliações físicas.

### Caso de Teste 01: Acesso à listagem de avaliações.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C10-CT01 | Verificar se a tela de avaliações é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                          |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                          |
| **QUANDO** acessarmos o menu "Avaliações"                                                                                           |
| **ENTÃO** a tela deverá exibir os filtros, os indicadores (Avaliação no Mês, Mês Passado e Média Mensal) e a listagem de avaliações |

| **Critérios de aceitação**                                                           |
| :----------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de avaliações com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Busca de avaliação pelo nome do aluno.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C10-CT02 | Verificar se a busca pelo nome retorna as avaliações do aluno. |

| **Pré-condições**                                                                |
| :------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem avaliações para o aluno pesquisado. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de avaliações                                                     |
| **E** informamos "rhanielly" no campo "Nome"                                                   |
| **QUANDO** clicarmos no botão "Buscar"                                                         |
| **ENTÃO** a listagem deverá exibir somente as avaliações da aluna Rhanielly Gabrielly Oliveira |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar a listagem pelo nome informado, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Filtro de avaliações por status.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C10-CT03 | Verificar se o filtro "Status" exibe somente as avaliações com o status selecionado. |

| **Pré-condições**                                                               |
| :------------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existirem avaliações pendentes e realizadas. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que estamos na tela de avaliações                                  |
| **E** selecionamos "Pendente" no filtro de status                           |
| **QUANDO** clicarmos no botão "Buscar"                                      |
| **ENTÃO** a listagem deverá exibir somente avaliações com status "PENDENTE" |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O sistema deve filtrar corretamente a listagem conforme o status selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastrar avaliação sem escolher o aluno.

| ID       | Descrição                          |
| :------- | :--------------------------------- |
| C10-CT04 | A avaliação não é salva sem aluno. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                  |
| :---------------------------------------------------------- |
| **DADO** que abrimos "Cadastrar Avaliação" em `/avaliacoes` |
| **E** não escolhemos o aluno                                |
| **QUANDO** clicamos em "Salvar"                             |
| **ENTÃO** o sistema pede para selecionar um aluno           |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema bloqueia o salvamento e mostra aviso sobre o aluno. |

| **Resultado da execução**                                                            |
| :----------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Selecione um aluno." e nenhuma requisição foi enviada. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Cadastro de avaliação sem hora.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C10-CT05 | Verificar se o sistema impede o cadastro da avaliação quando a hora não é informada. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Cadastrar Avaliação"                             |
| **E** selecionamos o aluno "Steven Kaiki" pela busca e o personal "Santhago"    |
| **E** não informamos a hora                                                     |
| **QUANDO** clicarmos no botão "Salvar"                                          |
| **ENTÃO** o sistema deverá apresentar a mensagem "Informe a hora da avaliação." |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que a hora seja informada. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Cadastro de avaliação com hora inválida.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C10-CT06 | Verificar se o sistema impede o cadastro da avaliação com hora inexistente. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                 |
| :--------------------------------------------------------- |
| **DADO** que abrimos a janela "Cadastrar Avaliação"        |
| **E** selecionamos o aluno "Lila" e o personal "Gabriella" |
| **E** informamos a hora "25:99"                            |
| **QUANDO** clicarmos no botão "Salvar"                     |
| **ENTÃO** o sistema deverá informar que a hora é inválida  |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| O sistema deve validar a hora informada antes de enviar o cadastro. |

| **Resultado da execução**                                              |
| :--------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro ao cadastrar Avaliação." (erro 500). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Cadastro de avaliação com dados válidos.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C10-CT07 | Verificar se a avaliação é agendada e passa a constar como pendente. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| O usuário deve estar autenticado e existir cliente cadastrado. |

| **Passos**                                                                                                                         |
| :--------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Cadastrar Avaliação"                                                                                |
| **E** selecionamos o aluno "Steven Kaiki", o personal "Santhago", a data atual e a hora "10:00"                                    |
| **QUANDO** clicarmos no botão "Salvar"                                                                                             |
| **ENTÃO** a avaliação deverá constar na listagem com status "PENDENTE" e a Página Inicial deverá contabilizar 1 avaliação pendente |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O sistema deve agendar a avaliação e exibi-la na listagem. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Alteração da data e hora da avaliação.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C10-CT08 | Verificar se a data e a hora de uma avaliação pendente podem ser alteradas. |

| **Pré-condições**                                                                                     |
| :---------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir avaliação pendente (ex.: Steven Kaiki, personal Santhago). |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de avaliações                            |
| **E** clicamos no botão "Alterar" da avaliação de Steven Kaiki        |
| **E** informamos a nova data "26/10/2026" e a nova hora "11:00"       |
| **QUANDO** clicarmos no botão "Salvar"                                |
| **ENTÃO** a listagem deverá exibir a avaliação em 26/10/2026 às 11:00 |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve salvar a nova data e hora e confirmar a alteração. |

| **Resultado da execução**                                                 |
| :------------------------------------------------------------------------ |
| **Falhou.** Nada acontece e a avaliação mantém a data e a hora originais. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Cálculo do IMC.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C10-CT09 | Verificar se o IMC é calculado e exibido corretamente ao informar altura e peso. |

| **Pré-condições**                                                                                     |
| :---------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir avaliação pendente (ex.: Steven Kaiki, personal Santhago). |

| **Passos**                                                           |
| :------------------------------------------------------------------- |
| **DADO** que clicamos em "Fazer Avaliação" de uma avaliação pendente |
| **E** informamos a altura "1,75" e o peso "80"                       |
| **QUANDO** o campo "IMC" for preenchido automaticamente              |
| **ENTÃO** o IMC deverá ser exibido como 26,12                        |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O IMC deve ser calculado e exibido com duas casas decimais. |

| **Resultado da execução**                              |
| :----------------------------------------------------- |
| **Falhou.** O IMC é exibido como "26.122448979591837". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Registro da avaliação realizada.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C10-CT10 | Verificar se a avaliação física é salva e passa a constar como realizada. |

| **Pré-condições**                                                                                     |
| :---------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir avaliação pendente (ex.: Steven Kaiki, personal Santhago). |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Fazer Avaliação" de uma avaliação pendente                                       |
| **E** informamos a altura "1,75" e o peso "80"                                                             |
| **QUANDO** clicarmos no botão "Salvar"                                                                     |
| **ENTÃO** a avaliação deverá constar com status "REALIZADO" e o botão "Visualizar" deverá ficar disponível |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve salvar a avaliação realizada e atualizar o status. |

| **Resultado da execução**                                                                |
| :--------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro ao salvar avaliação" e a avaliação permanece pendente. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Exclusão de avaliação.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C10-CT11 | Verificar se a avaliação é excluída ao confirmar a exclusão. |

| **Pré-condições**                                                                                     |
| :---------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir avaliação pendente (ex.: Steven Kaiki, personal Santhago). |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos na tela de avaliações                          |
| **E** clicamos no botão "Deletar" da avaliação de Steven Kaiki      |
| **QUANDO** confirmarmos a mensagem "Deseja deletar esta avaliação?" |
| **ENTÃO** a avaliação não deverá mais constar na listagem           |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O sistema deve solicitar confirmação e excluir a avaliação. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
