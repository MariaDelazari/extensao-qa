## Cenário 21: Modelos de contrato na plataforma SIFIT.

### Caso de Teste 01: Acesso à listagem de modelos de contrato.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C21-CT01 | Verificar se a tela exibe os modelos de contrato cadastrados. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem modelos de contrato cadastrados. |

| **Passos**                                                                               |
| :--------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                               |
| **QUANDO** acessarmos o menu "Modelos Contrato"                                          |
| **ENTÃO** a listagem deverá exibir o código, o nome e o status de cada modelo cadastrado |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve listar os modelos de contrato cadastrados. |

| **Resultado da execução**                                                                                                            |
| :----------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A listagem aparece vazia, só com os títulos das colunas. No DevTools (aba Network), a API retorna 9 modelos cadastrados. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/e1e3d8bf-996d-4aaa-9868-e8f046bfdf01) |

---

### Caso de Teste 02: Salvar modelo de contrato vazio.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C21-CT02 | Verificar se o sistema impede o cadastro de modelo sem título. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                     |
| :------------------------------------------------------------- |
| **DADO** que clicamos em "Adicionar Modelo Contrato"           |
| **E** deixamos o título e o texto do contrato vazios           |
| **QUANDO** clicarmos no botão "Salvar modelo"                  |
| **ENTÃO** o sistema deverá informar que o título é obrigatório |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o título seja informado. |

| **Resultado da execução**                                                            |
| :----------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o título do modelo." e o modelo não foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/1f86937d-e686-478a-a544-3b2b78cf2a2e) |

---

### Caso de Teste 03: Salvar modelo de contrato sem texto.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C21-CT03 | Verificar se o sistema impede o cadastro de modelo sem o texto do contrato. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Adicionar Modelo Contrato"                                  |
| **E** informamos o título "Contrato Teste Ville" e deixamos o texto do contrato vazio |
| **QUANDO** clicarmos no botão "Salvar modelo"                                         |
| **ENTÃO** o sistema deverá informar que o texto do contrato é obrigatório             |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| O sistema não deve salvar um modelo de contrato sem texto. |

| **Resultado da execução**                                                                        |
| :----------------------------------------------------------------------------------------------- |
| **Falhou.** O modelo "Contrato Teste Ville" foi salvo sem texto e a tela voltou para a listagem. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/648e27ae-8a17-496f-9886-1925dd6fc62a) |

---

### Caso de Teste 04: Inserção de variáveis no texto do contrato.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C21-CT04 | Verificar se a variável é inserida na posição do cursor. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que estamos no cadastro de modelo de contrato                            |
| **E** digitamos "Eu, " no texto do contrato                                       |
| **QUANDO** clicarmos na variável "{nome_aluno}" e continuarmos digitando ", CPF " |
| **ENTÃO** o texto deverá ficar "Eu, {nome_aluno}, CPF "                           |

| **Critérios de aceitação**                                                                     |
| :--------------------------------------------------------------------------------------------- |
| A variável deve ser inserida onde está o cursor e o texto seguinte deve continuar depois dela. |

| **Resultado da execução**                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A variável "{nome_aluno}" entrou onde estava o cursor e o texto ficou "Eu {nome_aluno} , CPF ,", na ordem digitada. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/275469f2-d6a9-4c74-bf1b-40865a698dd1) |

---

### Caso de Teste 05: Pré-visualização do contrato.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C21-CT05 | Verificar se a pré-visualização troca as variáveis por dados de exemplo. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que o texto do contrato tem as variáveis {nome_aluno}, {cpf_aluno} e {plano_nome}     |
| **QUANDO** clicarmos em "Atualizar preview"                                                    |
| **ENTÃO** a pré-visualização deverá exibir o texto com dados de exemplo no lugar das variáveis |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| A pré-visualização deve mostrar o contrato com as variáveis preenchidas. |

| **Resultado da execução**                                                                                         |
| :---------------------------------------------------------------------------------------------------------------- |
| **Passou.** A pré-visualização mostrou "João da Silva", "123.456.789-00" e "Plano Mensal" no lugar das variáveis. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/dbc50623-2b07-4c57-85aa-5a67c0fd999c) |

---

### Caso de Teste 06: Cadastro de modelo de contrato com dados válidos.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C21-CT06 | Verificar se o modelo é salvo e aparece na listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Adicionar Modelo Contrato"                                           |
| **E** informamos o título "Contrato Completo Ville", o status "Ativo" e um texto com variáveis |
| **QUANDO** clicarmos no botão "Salvar modelo"                                                  |
| **ENTÃO** o modelo deverá constar na listagem com status "ATIVO"                               |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| O sistema deve salvar o modelo e exibi-lo na listagem. |

| **Resultado da execução**                                                                                                                 |
| :---------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O modelo "Contrato Completo Ville" foi salvo e a tela voltou para a listagem, mas ele não aparece: a listagem continua vazia. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/fa52093b-2cba-4328-9ce9-fa00a0af85d5) |
