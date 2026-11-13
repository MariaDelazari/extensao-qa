## Cenário 18: Fichas de anamnese na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de fichas de anamnese.

| ID       | Descrição                                                                                                         |
| :------- | :---------------------------------------------------------------------------------------------------------------- |
| C18-CT01 | Verificar se a tela de fichas de anamnese é exibida com a busca, o filtro de status, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                            |
| :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                            |
| **QUANDO** acessarmos o menu "Fichas Anamnese"                                                                                                        |
| **ENTÃO** a tela deverá exibir a busca, o filtro de status, os indicadores (Total de fichas, Concluídas, Pendentes e Clientes avaliados) e a listagem |

| **Critérios de aceitação**                                                                   |
| :------------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de fichas de anamnese com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 02: Avançar sem selecionar aluno.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C18-CT02 | Verificar se o sistema impede avançar no assistente sem selecionar um aluno. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                               |
| :----------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Anamnese"                                 |
| **E** não selecionamos nenhum aluno                                      |
| **QUANDO** clicarmos no botão "Próxima"                                  |
| **ENTÃO** o sistema deverá informar que é necessário selecionar um aluno |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O assistente não deve avançar sem um aluno selecionado. |

| **Resultado da execução**                                                 |
| :------------------------------------------------------------------------ |
| **Falhou.** O assistente avança e a finalização exibe "Erro no servidor". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 03: Busca e seleção do aluno.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C18-CT03 | Verificar se o aluno é encontrado e selecionado no assistente. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o cliente "Steven Kaiki". |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Anamnese"                                                        |
| **E** informamos "Steven" no campo "Nome do aluno..." e clicamos na lupa                        |
| **QUANDO** clicarmos no aluno "Steven Kaiki" na lista                                           |
| **ENTÃO** o aluno deverá ser selecionado e o assistente deverá avançar para a escolha do modelo |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| O sistema deve localizar e selecionar o aluno. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 04: Exibição do aluno na escolha do modelo.

| ID       | Descrição                                                                    |
| :------- | :--------------------------------------------------------------------------- |
| C18-CT04 | Verificar se a etapa de escolha do modelo exibe o nome do aluno selecionado. |

| **Pré-condições**                                                          |
| :------------------------------------------------------------------------- |
| O usuário deve estar autenticado e ter selecionado o aluno "Steven Kaiki". |

| **Passos**                                                                                  |
| :------------------------------------------------------------------------------------------ |
| **DADO** que selecionamos o aluno "Steven Kaiki"                                            |
| **QUANDO** a etapa "Selecionar Modelo" for exibida                                          |
| **ENTÃO** o texto deverá exibir "Escolha o modelo de anamnese a aplicar para Steven Kaiki." |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| A etapa deve identificar o aluno selecionado. |

| **Resultado da execução**                          |
| :------------------------------------------------- |
| **Falhou.** O texto é exibido sem o nome do aluno. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 05: Exibição das perguntas do modelo.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C18-CT05 | Verificar se as perguntas do modelo selecionado são apresentadas para resposta. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o modelo "Triplet" com 1 pergunta. |

| **Passos**                                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| **DADO** que selecionamos o aluno "Steven Kaiki" e o modelo "Triplet" (1 pergunta)                   |
| **QUANDO** clicarmos no botão "Iniciar"                                                              |
| **ENTÃO** a pergunta do modelo deverá ser exibida para resposta antes da etapa "Revisar e Finalizar" |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| O assistente deve exibir todas as perguntas do modelo. |

| **Resultado da execução**                                                       |
| :------------------------------------------------------------------------------ |
| **Falhou.** O assistente pula para "Revisar e Finalizar" sem exibir a pergunta. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 06: Finalização da anamnese.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C18-CT06 | Verificar se a anamnese é salva ao clicar em "Finalizar Anamnese". |

| **Pré-condições**                                                        |
| :----------------------------------------------------------------------- |
| O usuário deve estar autenticado e estar na etapa "Revisar e Finalizar". |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que estamos na etapa "Revisar e Finalizar" da anamnese de Steven Kaiki |
| **QUANDO** clicarmos no botão "Finalizar Anamnese"                              |
| **ENTÃO** a anamnese deverá ser salva e o assistente deverá ser fechado         |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| O sistema deve salvar a anamnese aplicada. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 07: Listagem das anamneses aplicadas.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C18-CT07 | Verificar se a anamnese aplicada é exibida na listagem e nos indicadores. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e ter finalizado uma anamnese. |

| **Passos**                                                                                                                               |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que finalizamos a anamnese de Steven Kaiki                                                                                      |
| **QUANDO** acessarmos a tela de fichas de anamnese                                                                                       |
| **ENTÃO** a anamnese deverá constar na listagem e os indicadores "Total de fichas", "Concluídas" e "Clientes avaliados" deverão exibir 1 |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| O sistema deve exibir as anamneses aplicadas. |

| **Resultado da execução**                                                                 |
| :---------------------------------------------------------------------------------------- |
| **Falhou.** A listagem exibe "Nenhuma ficha encontrada" e os indicadores permanecem em 0. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |
