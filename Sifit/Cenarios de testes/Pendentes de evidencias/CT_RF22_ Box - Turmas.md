## Cenário 22: Box - Turmas (SifitBox) na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Box - Turmas.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C22-CT01 | Verificar se a tela exibe as modalidades e as turmas recorrentes. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                    |
| :---------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                    |
| **QUANDO** acessarmos o menu "Box - Turmas"                                                                                   |
| **ENTÃO** a tela deverá exibir os botões "Modalidade" e "Turma", a listagem de modalidades e a listagem de turmas recorrentes |

| **Critérios de aceitação**                                                          |
| :---------------------------------------------------------------------------------- |
| O sistema deve exibir a tela Box - Turmas com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Salvar modalidade vazia.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C22-CT02 | Verificar se o sistema orienta o usuário ao salvar modalidade sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                  |
| **E** deixamos o campo "Nome da modalidade" vazio                          |
| **QUANDO** clicarmos no botão "Modalidade"                                 |
| **ENTÃO** o sistema deverá informar que o nome da modalidade é obrigatório |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O sistema deve impedir o cadastro e informar o campo obrigatório. |

| **Resultado da execução**                                             |
| :-------------------------------------------------------------------- |
| **Falhou.** A modalidade não é salva, mas nenhuma mensagem é exibida. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Cadastro de modalidade com dados válidos.

| ID       | Descrição                               |
| :------- | :-------------------------------------- |
| C22-CT03 | Verificar se a modalidade é cadastrada. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                                                       |
| **E** informamos o nome "Modalidade Teste Ville", a descrição "Modalidade criada pelo Ville" e o status "Ativo" |
| **QUANDO** clicarmos no botão "Modalidade"                                                                      |
| **ENTÃO** a modalidade deverá constar na listagem como "ativo" e ficar disponível no cadastro de turmas         |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve cadastrar a modalidade e exibi-la na listagem. |

| **Resultado da execução**                                                                      |
| :--------------------------------------------------------------------------------------------- |
| **Passou.** A modalidade foi listada como "ativo" e apareceu no campo "Modalidade" das turmas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastro de modalidade duplicada.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C22-CT04 | Verificar se o sistema informa que a modalidade já existe. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a modalidade "Modalidade Teste Ville". |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que a modalidade "Modalidade Teste Ville" já está cadastrada |
| **E** informamos o mesmo nome no campo "Nome da modalidade"           |
| **QUANDO** clicarmos no botão "Modalidade"                            |
| **ENTÃO** o sistema deverá informar que a modalidade já existe        |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema deve informar ao usuário que a modalidade já existe. |

| **Resultado da execução**                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** A modalidade não é duplicada, mas nenhuma mensagem é exibida. No DevTools (aba Network), a API retorna erro 500 "Erro interno inesperado.". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Alteração de modalidade.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C22-CT05 | Verificar se os dados da modalidade podem ser alterados. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a modalidade "Modalidade Teste Ville". |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que clicamos no botão de editar da modalidade "Modalidade Teste Ville" |
| **E** alteramos o nome para "Modalidade Teste Ville Editada"                    |
| **QUANDO** clicarmos no botão "Modalidade"                                      |
| **ENTÃO** a listagem deverá exibir o nome atualizado                            |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| O sistema deve salvar as alterações da modalidade. |

| **Resultado da execução**                                                |
| :----------------------------------------------------------------------- |
| **Passou.** A listagem passou a exibir "Modalidade Teste Ville Editada". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Salvar turma vazia.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C22-CT06 | Verificar se o sistema orienta o usuário ao salvar turma sem dados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                 |
| :--------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                  |
| **E** deixamos os campos da turma vazios                   |
| **QUANDO** clicarmos no botão "Turma"                      |
| **ENTÃO** o sistema deverá informar os campos obrigatórios |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| O sistema deve impedir o cadastro e informar os campos obrigatórios. |

| **Resultado da execução**                                        |
| :--------------------------------------------------------------- |
| **Falhou.** A turma não é salva, mas nenhuma mensagem é exibida. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Cadastro de turma com dados válidos.

| ID       | Descrição                                     |
| :------- | :-------------------------------------------- |
| C22-CT07 | Verificar se a turma recorrente é cadastrada. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a modalidade "Modalidade Teste Ville". |

| **Passos**                                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                                                                                    |
| **E** informamos o nome "Turma Box Ville", a modalidade "Modalidade Teste Ville", o horário das 07:00 às 08:00, os dias Seg e Qua e 10 vagas |
| **QUANDO** clicarmos no botão "Turma"                                                                                                        |
| **ENTÃO** a turma deverá constar na listagem de turmas recorrentes                                                                           |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve cadastrar a turma e exibi-la na listagem. |

| **Resultado da execução**                                                       |
| :------------------------------------------------------------------------------ |
| **Passou.** A turma foi listada com o horário "07:00:00 - 08:00:00" e 10 vagas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Cadastro de turma com hora final anterior à inicial.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C22-CT08 | Verificar se o sistema impede turma com horário inválido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                                            |
| **E** informamos o nome "Turma Box Ville Horario", a modalidade "Modalidade Teste Ville" e o dia Ter |
| **E** informamos a hora inicial 11:00 e a hora final 10:00                                           |
| **QUANDO** clicarmos no botão "Turma"                                                                |
| **ENTÃO** o sistema deverá informar que a hora final deve ser maior que a hora inicial               |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| O sistema deve validar o horário da turma. |

| **Resultado da execução**                                             |
| :-------------------------------------------------------------------- |
| **Falhou.** A turma é cadastrada com o horário "11:00:00 - 10:00:00". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Cadastro de turma sem dias da semana.

| ID       | Descrição                                             |
| :------- | :---------------------------------------------------- |
| C22-CT09 | Verificar se o sistema impede turma sem dias de aula. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                   |
| :--------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                    |
| **E** informamos o nome "Turma Box Ville Sem Dia", a modalidade e o horário  |
| **E** não selecionamos nenhum dia da semana                                  |
| **QUANDO** clicarmos no botão "Turma"                                        |
| **ENTÃO** o sistema deverá informar que é preciso selecionar ao menos um dia |

| **Critérios de aceitação**                                                  |
| :-------------------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que ao menos um dia seja selecionado. |

| **Resultado da execução**                                  |
| :--------------------------------------------------------- |
| **Falhou.** A turma é cadastrada sem nenhum dia da semana. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 10: Cadastro de turma com vagas negativas.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C22-CT10 | Verificar se o sistema impede quantidade de vagas negativa. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela Box - Turmas                                             |
| **E** informamos o nome "Turma Box Ville Vagas", a modalidade, o horário e o dia Sex  |
| **E** informamos -5 no campo de vagas                                                 |
| **QUANDO** clicarmos no botão "Turma"                                                 |
| **ENTÃO** o sistema deverá informar que a quantidade de vagas deve ser maior que zero |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| O sistema deve aceitar somente quantidade de vagas maior que zero. |

| **Resultado da execução**                                |
| :------------------------------------------------------- |
| **Falhou.** A turma é cadastrada e listada com -5 vagas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Cadastro de turma com modalidade inativa.

| ID       | Descrição                                                           |
| :------- | :------------------------------------------------------------------ |
| C22-CT11 | Verificar se modalidades inativas ficam fora do cadastro de turmas. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a modalidade inativa "Leo valesk". |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que a modalidade "Leo valesk" está inativa                     |
| **QUANDO** abrirmos o campo "Modalidade" do cadastro de turma           |
| **ENTÃO** a modalidade inativa não deverá estar disponível para seleção |

| **Critérios de aceitação**                                                |
| :------------------------------------------------------------------------ |
| O sistema deve oferecer somente modalidades ativas no cadastro de turmas. |

| **Resultado da execução**                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A modalidade inativa "Leo valesk" aparece na lista e a turma "Turma Box Ville Inativa" foi cadastrada com ela. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 12: Alteração de turma.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C22-CT12 | Verificar se os dados da turma podem ser alterados. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir a turma "Turma Box Ville". |

| **Passos**                                                               |
| :----------------------------------------------------------------------- |
| **DADO** que clicamos no botão de editar da turma "Turma Box Ville"      |
| **E** alteramos o nome para "Turma Box Ville Editada" e as vagas para 15 |
| **QUANDO** clicarmos no botão "Turma"                                    |
| **ENTÃO** a listagem deverá exibir o nome e as vagas atualizados         |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| O sistema deve salvar as alterações da turma. |

| **Resultado da execução**                                                      |
| :----------------------------------------------------------------------------- |
| **Passou.** A listagem passou a exibir "Turma Box Ville Editada" com 15 vagas. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 13: Exclusão de turma.

| ID       | Descrição                                         |
| :------- | :------------------------------------------------ |
| C22-CT13 | Verificar se a turma é excluída após confirmação. |

| **Pré-condições**                                          |
| :--------------------------------------------------------- |
| O usuário deve estar autenticado e existir turma de teste. |

| **Passos**                                                                                 |
| :----------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Box - Turmas                                                  |
| **QUANDO** clicarmos no botão de excluir da turma "Turma Box Ville Horario"                |
| **ENTÃO** o sistema deverá pedir confirmação e a turma não deverá mais constar na listagem |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| O sistema deve solicitar confirmação e retirar a turma da listagem. |

| **Resultado da execução**                                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há confirmação e a turma continua na listagem. Pela API, a turma só passa para "inativo", mas a listagem não tem coluna de status. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
