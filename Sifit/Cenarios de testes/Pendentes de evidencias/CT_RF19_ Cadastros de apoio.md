## Cenário 19: Validação dos cadastros de apoio (campos obrigatórios).

### Caso de Teste 01: Salvar Bandeiras de Cartão com o formulário vazio.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C19-CT01 | O cadastro de Bandeiras de Cartão não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Bandeira" em `/bandeiras`                  |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                              |
| :------------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o nome da bandeira." e o cadastro não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Salvar Pontuação com o formulário vazio.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C19-CT02 | O cadastro de Pontuação não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Pontuação" em `/pontuacao`                 |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                               |
| :-------------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o nome da pontuação." e o cadastro não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Salvar Enquetes com o formulário vazio.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C19-CT03 | O cadastro de Enquetes não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Enquete" em `/enquetes`                    |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução**                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao salvar a enquete sem preencher nada, a tela mostrou "Erro ao salvar enquete", sem indicar o que falta. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Salvar Atividades com o formulário vazio.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C19-CT04 | O cadastro de Atividades não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Atividade" em `/atividades`                |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução**                                                                                 |
| :-------------------------------------------------------------------------------------------------------- |
| **Falhou.** O formulário vazio foi salvo: a lista passou de 4 para 5 atividades, com a linha 5 em branco. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Salvar Tipos de Documentos com o formulário vazio.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C19-CT05 | O cadastro de Tipos de Documentos não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Novo Tipo" em `/tipos-documento`                |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                                       |
| :---------------------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o nome do tipo de documento." e o cadastro não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Salvar Categorias Crossfit com o formulário vazio.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C19-CT06 | O cadastro de Categorias Crossfit não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Categoria" em `/categorias-exercicios-crossfit` |
| **E** deixamos todos os campos vazios                                      |
| **QUANDO** clicamos em "Salvar"                                            |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro      |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução**                                                               |
| :-------------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o nome da categoria." e o cadastro não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 07: Salvar Objetivos de Treino com o formulário vazio.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C19-CT07 | O cadastro de Objetivos de Treino não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Novo Objetivo" em `/objetivos-treino`           |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução**                                                                               |
| :------------------------------------------------------------------------------------------------------ |
| **Falhou.** O formulário vazio foi salvo: a lista passou de 0 para 1 objetivo, com a linha 1 em branco. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 08: Salvar Tipos de Pagamento com o formulário vazio.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C19-CT08 | O cadastro de Tipos de Pagamento não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Novo" em `/tipos-pagamento`                     |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução**                                                                               |
| :------------------------------------------------------------------------------------------------------ |
| **Falhou.** O formulário vazio foi salvo: a lista passou de 10 para 11 tipos, com a linha 12 em branco. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 09: Salvar Perguntas de Anamnese com o formulário vazio.

| ID       | Descrição                                                                                   |
| :------- | :------------------------------------------------------------------------------------------ |
| C19-CT09 | O cadastro de Perguntas de Anamnese não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Pergunta" em `/perguntas-anamnese`         |
| **E** deixamos todos os campos vazios                                 |
| **QUANDO** clicamos em "Salvar"                                       |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação**                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução**                                                                                                |
| :----------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao salvar a pergunta sem preencher nada, a tela mostrou só "Erro ao salvar pergunta", sem dizer o que falta. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
