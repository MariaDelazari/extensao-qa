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

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/5c5ffa14-3471-4ac3-ae23-350e61f664a2) |

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

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2a172b08-7d5c-479f-8693-bb73d203b5fb) |

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

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/dd7d65bf-73c2-44c1-90b5-4c508e583251) |

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
| **Falhou.** O formulário vazio foi salvo: a lista passou de 7 para 8 atividades, com a linha 8 em branco. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/38fffd95-5da2-45ca-8f34-3494850a1658) |

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

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/99195cbc-6cf8-48ed-8fe7-4d031477a555) |

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

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/0523ac03-e54f-4962-8ce4-5b389dab383f) |

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

| **Resultado da execução**                                                                                 |
| :-------------------------------------------------------------------------------------------------------- |
| **Falhou.** O formulário vazio foi salvo: a lista passou de 7 para 8 objetivos, com o código 9 em branco. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/c9c3d7ea-9cca-4eaa-b867-a3699a4fd485) |

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

| **Resultado da execução**                                                                                |
| :------------------------------------------------------------------------------------------------------- |
| **Falhou.** O formulário vazio foi salvo: a lista passou de 19 para 20 tipos, com o código 25 em branco. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/74ea4701-c61e-48eb-863f-a931c5d5d9b8) |

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

| **Resultado da execução**                                                                                                                                  |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Ao salvar a pergunta sem preencher nada, a tela mostrou só "Erro ao salvar pergunta", sem dizer o que falta, e a requisição retornou erro 500. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/841a6835-d43d-4ca1-82bc-772d6587b1e6) |

---

### Caso de Teste 10: Cadastro de bandeira de cartão com dados válidos.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C19-CT10 | A bandeira de cartão cadastrada aparece na listagem. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Bandeira" em `/bandeiras`                                                       |
| **E** informamos o nome "Bandeira", a taxa adicional 10,00, a taxa débito 5,00 e a parcela 1 com taxa 2,00 |
| **QUANDO** clicamos em "Salvar"                                                                            |
| **ENTÃO** a bandeira aparece na listagem                                                                   |

| **Critérios de aceitação**                |
| :---------------------------------------- |
| A bandeira é salva e aparece na listagem. |

| **Resultado da execução**                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** A bandeira foi criada (resposta 201), mas a listagem continuou com "Nenhuma bandeira encontrada.", inclusive depois de recarregar a página. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/cbf1a04a-129c-4ee1-a09d-791c326cbc26) |

---

### Caso de Teste 11: Cadastro de pontuação com dados válidos.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C19-CT11 | A pontuação cadastrada com período válido aparece na listagem. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Pontuação" em `/pontuacao`                                                      |
| **E** informamos o nome "frequencia", o período de 01/11/2026 a 30/11/2026, o tipo Mensal e o status Ativo |
| **QUANDO** clicamos em "Salvar"                                                                            |
| **ENTÃO** a pontuação aparece na listagem com o período informado                                          |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| A pontuação é salva e aparece na listagem com o período certo. |

| **Resultado da execução**                                                                                                    |
| :--------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A pontuação foi salva, o total passou de 6 para 7 e a busca por "fre" mostrou o período 2026-11-01 — 2026-11-30. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/775b133f-fc89-442b-af7a-e2038a3b0307) |

---

### Caso de Teste 12: Cadastro de pontuação com data final anterior à inicial.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C19-CT12 | O cadastro de pontuação não aceita data final anterior à data inicial. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que abrimos "Nova Pontuação" em `/pontuacao`                                         |
| **E** informamos o nome "Primeiro lugar", a data inicial 30/11/2026 e a data final 02/11/2026 |
| **QUANDO** clicamos em "Salvar"                                                               |
| **ENTÃO** o sistema informa que a data final deve ser posterior à inicial e não salva         |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema bloqueia o período invertido e avisa a pessoa. |

| **Resultado da execução**                                                                            |
| :--------------------------------------------------------------------------------------------------- |
| **Falhou.** A pontuação foi salva sem aviso e a listagem mostra o período "2026-11-30 — 2026-11-02". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/833e99ee-b5f7-4568-88fd-e40b7b818da6) |
