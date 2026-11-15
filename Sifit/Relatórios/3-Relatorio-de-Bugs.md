# Relatório de Bugs

**Software:** Sifit Centrion

**Versão:** Sifit Centrion e Sifit Unialfa

**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, https://sifitalfa.centrion.com.br/

**QA responsável:** Maria Eduarda Pacheco Delazari, RA: 240017; Ville Nunes Figueiredo da Silva, RA: 14534; Keltton Felipe Alves Silveira, RA: 14509; Daniel Satel Pereira, RA: 14567; Rafael Colombo da Silva, RA: 14551

**Data:** 12.10.26. Em 24/10/2026, os testes continuaram no Sifit Unialfa. Os bugs foram observados entre 12/10/2026 e 28/10/2026; o ambiente de cada um está na própria tabela.

---

### 🐞 **Bug 01: Falha no login ao inserir espaços extras nas credenciais válidas**

| **ID**  | **Descrição**                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-001 | Ao inserir credenciais válidas com espaços extras no início ou no final dos campos de login, o sistema impede a autenticação, mesmo quando as credenciais são válidas. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                 |
| ------------------------------------------------------------------------------------ |
| 1. Acessar a página de login.                                                        |
| 2. Inserir um nome de usuário válido com espaços extras no início ou no final.       |
| 3. Inserir uma senha válida, adicionando espaços extras conforme o cenário de teste. |
| 4. Clicar no botão verde "Entrar".                                                   |
| 5. Verificar se a autenticação é realizada corretamente.                             |

|                                                                     **Comportamento Esperado**                                                                     |                                                                                                            **Comportamento Obtido**                                                                                                            |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve tratar adequadamente os espaços extras no início e no final dos campos de credenciais, permitindo o login quando os dados informados forem válidos. | O sistema rejeita o login quando há espaços extras nos campos de credenciais e exibe a mensagem "Nome de usuário e senha não correspondem", mesmo com dados válidos, levando o usuário a acreditar que informou as credenciais incorretamente. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

| **Funcionalidade Afetada** |                **Caso de Teste Relacionado**                |
| :------------------------: | :---------------------------------------------------------: |
|    Login / Autenticação    | C01-CT04: Login com espaços extras nas credenciais válidas. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:01](https://jam.dev/c/51531b19-254b-468b-ad89-7487194fc22a) |

---

### 🐞 **Bug 02: Link "Esqueci minha senha" não funciona**

| **ID**  | **Descrição**                                                                                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-002 | Ao clicar no link "Esqueci minha senha" na tela de login, o sistema não realiza nenhum redirecionamento, impedindo o acesso à funcionalidade de recuperação de senha. O link aponta para "#" e não abre tela nem janela. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                    |
| 2. Localizar o link "Esqueci minha senha".                                       |
| 3. Clicar no link.                                                               |
| 4. Verificar se ocorre o redirecionamento para a página de recuperação de senha. |

|                                         **Comportamento Esperado**                                          |                                    **Comportamento Obtido**                                     |
| :---------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| O sistema deve direcionar o usuário para a página de recuperação de senha ao clicar no link correspondente. | Ao clicar no link, nenhum redirecionamento é realizado, e o usuário permanece na tela de login. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|  **Funcionalidade Afetada**  |      **Caso de Teste Relacionado**       |
| :--------------------------: | :--------------------------------------: |
| Login / Recuperação de senha | C01-CT07: Acesso à recuperação de senha. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:02](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

---

### 🐞 **Bug 03: Erro interno do servidor ao validar credenciais inválidas no login**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-003 | Ao inserir uma senha incorreta na tela de login, a requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.". A resposta da API contém `"verifica_erro": true`, indicando uma falha, mas não identifica o problema como credenciais inválidas. O sistema deveria tratar a tentativa como uma falha de autenticação e apresentar uma mensagem clara ao usuário. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                                                  |
| --------------------------------------------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                                                         |
| 2. Inserir um nome de usuário válido.                                                                                 |
| 3. Inserir uma senha incorreta.                                                                                       |
| 4. Clicar no botão verde "Entrar".                                                                                    |
| 5. Verificar a resposta da requisição `POST /api/login` na aba Network das ferramentas de desenvolvedor do navegador. |

|                                                                                               **Comportamento Esperado**                                                                                               |                                                                                             **Comportamento Obtido**                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve validar as credenciais informadas e, caso sejam inválidas, retornar uma resposta apropriada de falha de autenticação, como "Nome de usuário ou senha inválidos", sem gerar um erro interno do servidor. | A requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.", em vez de informar que as credenciais estão incorretas. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**           |
| :------------------------: | :-----------------------------------------------: |
|    Login / Autenticação    | C01-CT02: Tentativa de login com senha incorreta. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:03](https://jam.dev/c/a6cbb545-f415-4e44-b446-20f146f32a1c) |

---

### 🐞 **Bug 04: Ausência de validação de campos obrigatórios no login**

| **ID**  | **Descrição**                                                                                                                                                             |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-004 | Ao tentar realizar o login com os campos de nome de usuário e senha vazios, o sistema permite o envio da requisição à API sem validar previamente os campos obrigatórios. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                           |
| ---------------------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                                  |
| 2. Manter os campos de nome de usuário e senha vazios.                                         |
| 3. Clicar no botão verde "Entrar".                                                             |
| 4. Verificar a resposta da API e as mensagens exibidas na interface e no console do navegador. |

|                                                                **Comportamento Esperado**                                                                |                                                                                                                                                                                       **Comportamento Obtido**                                                                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve validar os campos obrigatórios antes de enviar a requisição, informando ao usuário que o nome de usuário e a senha devem ser preenchidos. | O sistema envia a requisição à API mesmo com os campos vazios. A API retorna uma resposta vazia (`[]`), e a mensagem padrão de credenciais inválidas aparece no console do navegador. A interface não informa que os campos são obrigatórios, e o usuário permanece na tela de login. A tela mostra a mesma mensagem usada para credenciais inválidas: "O nome de usuário e senha não correspondem." |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|        **Funcionalidade Afetada**        |                **Caso de Teste Relacionado**                 |
| :--------------------------------------: | :----------------------------------------------------------: |
| Login / Validação de campos obrigatórios | C01-CT03: Tentativa de login com campos obrigatórios vazios. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:04](https://jam.dev/c/fcd3f7a9-9e1b-4aa3-a683-f5155d753e53) |

---

### 🐞 **Bug 05: Falha na persistência e no controle da sessão de login**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-005 | Ao marcar a opção "Manter conectado" e retornar ao sistema Sifit, o usuário é redirecionado à tela de login e precisa informar suas credenciais novamente, mesmo tendo selecionado essa opção. Entretanto, ao permanecer na tela de login e inserir diretamente a URL `/dashboard` no navegador, o sistema permite o acesso à área autenticada sem solicitar novamente o login. Dessa forma, o sistema apresenta duas falhas: não mantém o usuário conectado conforme esperado e permite o acesso ao dashboard diretamente pela URL, sem exigir autenticação. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                                        |
| ----------------------------------------------------------------------------------------------------------- |
| 1. Acessar a tela de login do sistema Sifit Centrion.                                                       |
| 2. Informar credenciais válidas nos campos de nome de usuário e senha.                                      |
| 3. Marcar a opção "Manter conectado".                                                                       |
| 4. Clicar no botão "Entrar" e abrir o sistema em uma nova aba do navegador.                                 |
| 5. Retornar à tela de login e verificar se o sistema solicita novamente as credenciais.                     |
| 6. Permanecer na tela de login e inserir diretamente a URL `/dashboard` na barra de endereços do navegador. |
| 7. Verificar se o sistema permite o acesso ao dashboard sem solicitar autenticação novamente.               |

|                                                                                                                                                                                                  **Comportamento Esperado**                                                                                                                                                                                                   |                                                                                                                                                                   **Comportamento Obtido**                                                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Ao marcar a opção "Manter conectado", o sistema deve manter a autenticação do usuário ao retornar à aplicação, conforme o comportamento esperado dessa funcionalidade. Caso o usuário não possua uma sessão válida, o sistema deve bloquear o acesso ao dashboard, inclusive quando a URL `/dashboard` for inserida diretamente na barra de endereços do navegador, redirecionando-o à tela de login e exigindo autenticação. | Ao marcar a opção "Manter conectado", o usuário é redirecionado à tela de login ao retornar ao sistema e precisa informar suas credenciais novamente. Entretanto, ao permanecer na tela de login e inserir diretamente a URL `/dashboard` na barra de endereços do navegador, o sistema permite o acesso à área autenticada sem solicitar novamente o login. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|             **Funcionalidade Afetada**              |                                       **Caso de Teste Relacionado**                                       |
| :-------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Login / Persistência da sessão / Controle de acesso | C01-CT05: Persistência da sessão com "Manter conectado". C01-CT06: Acesso ao dashboard sem sessão válida. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:05](https://jam.dev/c/0e862f82-e4d0-49df-9406-0ff970332873) |

---

### 🐞 **Bug 06: Erro interno do servidor ao autenticar com credenciais válidas**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-006 | Ao informar credenciais válidas na tela de login e tentar acessar o sistema, a requisição `POST /api/login` para o endpoint de autenticação retorna o status `500 Internal Server Error`. A resposta da API contém `"verifica_erro": true` e a mensagem `"Erro interno inesperado."`, impedindo a conclusão da autenticação. Dessa forma, o usuário não consegue acessar o sistema, mesmo informando as credenciais da conta de teste. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                       |
| ------------------------------------------------------------------------------------------ |
| 1. Acessar a tela de login do sistema Sifit Centrion.                                      |
| 2. Informar as credenciais válidas da conta de teste.                                      |
| 3. Clicar no botão "Entrar".                                                               |
| 4. Abrir as ferramentas de desenvolvedor do navegador e acessar a aba Network.             |
| 5. Localizar a requisição `POST /api/login` e verificar o status e o conteúdo da resposta. |
| 6. Verificar se a autenticação é concluída e se o usuário consegue acessar o sistema.      |

|                                                           **Comportamento Esperado**                                                           |                                                                                                 **Comportamento Obtido**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Ao informar credenciais válidas, o sistema deve autenticar o usuário e permitir o acesso à aplicação, sem retornar erros internos do servidor. | A requisição `POST /api/login` retorna o status `500 Internal Server Error`. A resposta da API contém `"verifica_erro": true` e a mensagem `"Erro interno inesperado."`, impedindo a autenticação e o acesso ao sistema. |

| **Ambiente**                |
| --------------------------- |
| Ambiente de testes          |
| Desktop Ubuntu 26.04 LTS    |
| Google Chrome 150.0.7871.46 |
| Sifit Centrion              |

|          **Funcionalidade Afetada**          |      **Caso de Teste Relacionado**       |
| :------------------------------------------: | :--------------------------------------: |
| Login / Autenticação com credenciais válidas | C01-CT01: Login com credenciais válidas. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:06](https://jam.dev/c/070f284b-e3a2-4514-8fe3-4290f33d77ee) |

---

### 🐞 **Bug 07: Inconsistência na identificação do usuário e na autenticação**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-007 | Ao tentar realizar o login com o usuário `marcelo_zandonadi`, o sistema exibe a mensagem "O nome de usuário e senha não correspondem", impedindo a autenticação. Na mesma gravação, é exibido o perfil de um usuário identificado como Jair, porém não há informação visível no perfil que permita confirmar se esse nome está associado ao login utilizado na tentativa de autenticação. Dessa forma, não é possível confirmar a correspondência entre o usuário informado no login e o perfil apresentado no sistema. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                                                       |
| -------------------------------------------------------------------------------------------------------------------------- |
| 1. Acessar a tela de login do sistema Sifit Centrion.                                                                      |
| 2. Informar o usuário `marcelo_zandonadi` e a senha da conta de teste.                                                     |
| 3. Clicar no botão "Entrar".                                                                                               |
| 4. Verificar a mensagem apresentada pelo sistema após a tentativa de autenticação.                                         |
| 5. Acessar o perfil exibido na gravação e verificar os dados disponíveis sobre a identificação do usuário.                 |
| 6. Verificar se existe alguma informação que relacione o nome apresentado no perfil ao nome de usuário utilizado no login. |

|                                                                    **Comportamento Esperado**                                                                    |                                                                                                                  **Comportamento Obtido**                                                                                                                  |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve permitir a autenticação quando as credenciais forem válidas e apresentar informações que permitam identificar corretamente o usuário autenticado. | A tentativa de login com `marcelo_zandonadi` é rejeitada com a mensagem "O nome de usuário e senha não correspondem". O perfil exibido posteriormente apresenta o nome Jair, mas não há informação visível que confirme sua relação com o login utilizado. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |

|           **Funcionalidade Afetada**            |                               **Caso de Teste Relacionado**                                |
| :---------------------------------------------: | :----------------------------------------------------------------------------------------: |
| Login / Autenticação / Identificação do usuário | C01-CT01: Login com credenciais válidas. C02-CT01: Abrir a página inicial depois do login. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:07](https://jam.dev/c/ca20044a-89b1-4723-b121-2863cfb8d4a7) |

---

### 🐞 **Bug 08: Radar de Evasão mostra a faixa errada de alunos**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-008 | No Sifit Unialfa, o detalhe "Radar de Evasão" informa no rodapé que está exibindo os alunos 3 a 4 de um total de 4. A tabela visível no mesmo quadro lista quatro alunos. O botão "Exportar relatório" é acionado várias vezes na gravação, sem mensagem de confirmação. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                   |
| ---------------------------------------------------------------------- |
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard.              |
| 2. Abrir o detalhe dos alunos em risco de evasão.                      |
| 3. Conferir o rodapé "Exibindo..." e a quantidade de linhas da tabela. |
| 4. Clicar em "Exportar relatório".                                     |

|                                               **Comportamento Esperado**                                                |                                                                                                                          **Comportamento Obtido**                                                                                                                          |
| :---------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O rodapé deve indicar a faixa real de linhas visíveis. O exportar deve gerar o relatório ou avisar se não foi possível. | Em 25/10/2026, o rodapé aparece como "Exibindo 3 a 4 de 4 alunos em risco", com quatro linhas na tabela. A gravação não mostra o arquivo exportado nem um aviso. O Jam desse vídeo não trouxe registro de rede, então não dá para afirmar que a requisição deixou de sair. |

| **Ambiente**                                |
| ------------------------------------------- |
| Sifit Unialfa                               |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS                    |
| Google Chrome 150.0.7871.46                 |
| 25/10/2026                                  |

|    **Funcionalidade Afetada**    |                         **Caso de Teste Relacionado**                         |
| :------------------------------: | :---------------------------------------------------------------------------: |
| Página inicial / Radar de Evasão | C02-CT02: Radar de evasão. C02-CT10: Conferir os cards do resumo da academia. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:08](https://jam.dev/c/fa584de0-d641-465a-a2b3-d0a311bc1c5a) |

---

### 🐞 **Bug 09: Cobrança e perfil de Rafael Santos não fecham com a lista**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                 |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-009 | Na cobrança de Rafael Santos pelo WhatsApp, a tela mostra mensalidade de R$ 350,00 e multa de R$ 1,00, mas o total atualizado é R$ 375,59. A mensagem pronta repete esse total. Na mesma gravação, a lista de clientes mostra o aluno 398 com plano Treino Personal e status ATIVO, e o perfil dele mostra "Sem matrícula" e "Sem registros". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                         |
| ---------------------------------------------------------------------------- |
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard.                    |
| 2. Abrir a cobrança de Rafael Santos, vencimento 12/05/2026.                 |
| 3. Comparar valor, multa e total atualizado na janela "Cobrar via WhatsApp". |
| 4. Abrir Clientes, localizar o código 398 e entrar em Visualizar Cliente.    |
| 5. Comparar plano e matrícula da lista com os do perfil.                     |

|                                                                       **Comportamento Esperado**                                                                        |                                                                                    **Comportamento Obtido**                                                                                    |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O total da cobrança deve ser a soma dos valores apresentados, ou a tela deve mostrar a parcela que falta. O plano e a matrícula do perfil devem ser os mesmos da lista. | O total fica em R$ 375,59, e a multa exibida é R$ 1,00. A lista diz Treino Personal e ATIVO. O perfil diz Sem matrícula, 0/3 aulas e sem registros. O vencimento visto no perfil é 08/07/2026. |

| **Ambiente**                                |
| ------------------------------------------- |
| Sifit Unialfa                               |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS                    |
| Google Chrome 150.0.7871.46                 |
| 25/10/2026                                  |

|          **Funcionalidade Afetada**           |           **Caso de Teste Relacionado**            |
| :-------------------------------------------: | :------------------------------------------------: |
| Página inicial / Cobrança e cadastro do aluno | C02-CT10: Conferir os cards do resumo da academia. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:09](https://jam.dev/c/cca56c7a-000b-43b7-9fb8-2012e445ee9a) |

---

### 🐞 **Bug 10: Card de valor em aberto não confere com o detalhe**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                             |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-010 | Na página inicial do Sifit Unialfa, o card mostra R$ 200,00 em aberto. Ao abrir "Financeiro em Aberto", o total exibido é R$ 450,00. A linha de Rafael Santos mostra R$ 350,00 e um acréscimo de R$ 100,00. Em 23/10/2026, no sifit.centrion.com.br, com contas pendentes no período, o card mostrou "R$ 0,00 em aberto". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                                  |
| ----------------------------------------------------------------------------------------------------- |
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard.                                             |
| 2. Anotar o valor do card "em aberto".                                                                |
| 3. Abrir o detalhe Financeiro em Aberto.                                                              |
| 4. Comparar o total do detalhe, a quantidade de alunos em atraso e o valor da linha de Rafael Santos. |

|                                    **Comportamento Esperado**                                    |                                                                     **Comportamento Obtido**                                                                      |
| :----------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O total do detalhe deve ser o mesmo valor do card, e a soma das linhas deve explicar esse total. | O card mostra R$ 200,00. O detalhe mostra R$ 450,00, com 2 alunos em atraso e 8 mensalidades. A linha visível de Rafael Santos está em R$ 350,00, com +R$ 100,00. |

| **Ambiente**                                |
| ------------------------------------------- |
| Sifit Unialfa                               |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS                    |
| Google Chrome 150.0.7871.46                 |
| 25/10/2026                                  |

|       **Funcionalidade Afetada**        |           **Caso de Teste Relacionado**            |
| :-------------------------------------: | :------------------------------------------------: |
| Página inicial / Mensalidades em aberto | C02-CT10: Conferir os cards do resumo da academia. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:10](https://jam.dev/c/63ec10f5-e5b6-4150-a1f6-8e0c1978f806) |

---

### 🐞 **Bug 11: O campo de senha não deixa ver o que foi digitado**

| **ID**  | **Descrição**                                                                                                                                                  |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-011 | Na tela de login, o campo de senha não tem ícone nem outra opção para mostrar os caracteres. A pessoa não consegue conferir a senha antes de clicar em Entrar. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                           |
| -------------------------------------------------------------- |
| 1. Abrir a tela de login.                                      |
| 2. Clicar no campo de senha.                                   |
| 3. Digitar uma senha.                                          |
| 4. Procurar um ícone ou botão para mostrar o que foi digitado. |

|                                             **Comportamento Esperado**                                              |                     **Comportamento Obtido**                     |
| :-----------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------: |
| O campo deve ter um controle para mostrar e esconder a senha, para a pessoa conferir o que digitou antes de entrar. | A senha fica oculta o tempo todo. Não há controle para exibi-la. |

| **Ambiente**                 |
| ---------------------------- |
| Sifit Centrion               |
| Desktop com Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46  |

| **Funcionalidade Afetada** |      **Caso de Teste Relacionado**       |
| :------------------------: | :--------------------------------------: |
|   Login / Campo de senha   | C01-CT01: Login com credenciais válidas. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:11](https://jam.dev/c/1c6d4e56-7c8b-43d3-9134-c3bde64d0d80) |

---

### 🐞 **Bug 12: Dashboard mostra o título "Despesas Fixas"**

| **ID**  | **Descrição**                                                                                                |
| ------- | ------------------------------------------------------------------------------------------------------------ |
| BUG-012 | Ao abrir a página Dashboard pelo menu, o título da página e o caminho de navegação mostram "Despesas Fixas". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                          |
| ------------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                                   |
| 2. Clicar em "Dashboard" no menu lateral (rota `/dash`).      |
| 3. Olhar o título da página e o caminho de navegação no topo. |

|                  **Comportamento Esperado**                  |                                          **Comportamento Obtido**                                          |
| :----------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------: |
| O título e o caminho de navegação devem mostrar "Dashboard". | O topo mostra "Início > Despesas Fixas" e o título "Despesas Fixas", enquanto o conteúdo é o do Dashboard. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|  **Funcionalidade Afetada**  |    **Caso de Teste Relacionado**    |
| :--------------------------: | :---------------------------------: |
| Dashboard / Título da página | C03-CT01: Abrir a página Dashboard. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:12](https://jam.dev/c/fbc8ddfc-e244-413c-995b-c8bee8733105) |

---

### 🐞 **Bug 13: Títulos dos gráficos do Dashboard ficam ilegíveis**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                 |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-013 | No Dashboard, os títulos dos blocos de gráficos e dos próprios gráficos quase não aparecem, por causa da cor do texto sobre o fundo. No modo claro, os títulos das seções ficam em branco sobre fundo claro, e os títulos dos gráficos (por exemplo "FREQUÊNCIA" e "POR MÊS") ficam em cinza-escuro (rgb 31, 41, 55) sobre o fundo azul-marinho dos cartões (rgb 23, 43, 77). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                                    |
| ------------------------------------------------------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa, com o tema Claro.                                                           |
| 2. Abrir o Dashboard (`/dash`).                                                                         |
| 3. Rolar a página olhando os blocos Clientes, Matrículas, Contas a Receber, Cancelamentos e Avaliações. |

|                              **Comportamento Esperado**                               |                                                              **Comportamento Obtido**                                                              |
| :-----------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------: |
| Os títulos dos blocos e dos gráficos devem ter contraste suficiente para serem lidos. | Os títulos (por exemplo "Clientes", "Matrículas", "Frequência", "Idade", "Sexo") aparecem em cor muito próxima à do fundo e quase não dá para ler. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |        **Caso de Teste Relacionado**        |
| :------------------------: | :-----------------------------------------: |
|    Dashboard / Gráficos    | C03-CT02: Conferir os títulos dos gráficos. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:13](https://jam.dev/c/72ff4074-832d-451e-908c-674402829bf3) |

---

### 🐞 **Bug 14: Quantidade de alunos em risco diverge entre as telas**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-014 | A quantidade de alunos em risco é diferente na Página Inicial, na Inteligência de Retenção da Página Inicial e no Dashboard. Em outra medição, o card da Página Inicial e o "Radar de Evasão" mostraram 3 alunos, a Inteligência de Retenção mostrou 4 em médio risco e o Dashboard mostrou 0. O Radar também informa último treino "Há 15 dias" para alunos que nunca registraram visita. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                            |
| ----------------------------------------------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa e olhar o card "alunos em risco de evasão" da Página Inicial.        |
| 2. Na mesma página, olhar os totais de Alto, Médio e Baixo risco de "Inteligência de Retenção". |
| 3. Abrir o Dashboard (`/dash`) e olhar o card "Alunos em risco".                                |

|              **Comportamento Esperado**               |                                                                       **Comportamento Obtido**                                                                       |
| :---------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| A mesma quantidade de alunos em risco nas três áreas. | Em 28/10/2026: Página Inicial mostra "1 alunos em risco de evasão"; Inteligência de Retenção mostra 0 alto, 4 médio e 0 baixo; Dashboard mostra "0 Alunos em risco". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|          **Funcionalidade Afetada**          |                          **Caso de Teste Relacionado**                           |
| :------------------------------------------: | :------------------------------------------------------------------------------: |
| Página inicial e Dashboard / Alunos em risco | C03-CT03: Conferir os alunos em risco entre as telas. C02-CT02: Radar de evasão. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:14](https://jam.dev/c/5d2ad698-91fa-4d9f-a9f0-64f26dc274dc) |

---

### 🐞 **Bug 15: Card de avaliações pendentes mostra 1, mas a lista tem 5 pendentes**

| **ID**  | **Descrição**                                                                                                                  |
| ------- | ------------------------------------------------------------------------------------------------------------------------------ |
| BUG-015 | O card da Página Inicial mostra "1 avaliações pendentes", mas a lista de avaliações filtrada por Pendente mostra 5 avaliações. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                 |
| ------------------------------------------------------------------------------------ |
| 1. Entrar no Sifit Unialfa e olhar o card de avaliações pendentes da Página Inicial. |
| 2. Clicar em "Ver detalhes" do card (rota `/avaliacoes?status=pendente`).            |
| 3. Contar as linhas da lista com status PENDENTE.                                    |

|                           **Comportamento Esperado**                           |                                                       **Comportamento Obtido**                                                        |
| :----------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------: |
| O número do card deve ser igual à quantidade de avaliações pendentes da lista. | O card mostra "1 avaliações pendentes". A lista abre com o filtro Pendente e mostra 5 avaliações PENDENTE (#95, #79, #69, #67 e #52). |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 15/11/2026                         |

|      **Funcionalidade Afetada**       |           **Caso de Teste Relacionado**            |
| :-----------------------------------: | :------------------------------------------------: |
| Página inicial / Avaliações pendentes | C02-CT08: Abrir as avaliações pendentes pelo card. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:15](https://jam.dev/c/32d0c4a0-db6d-4f38-9f3a-eeceee068739) |

---

### 🐞 **Bug 16: Paginação de clientes mostra 3 páginas para 1 resultado**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-016 | Na lista de clientes com o filtro Status "Ativo", a tabela tem 1 cliente, mas a paginação oferece as páginas 1, 2 e 3. A falha também aparece com 5 clientes ativos (as páginas 2 e 3 abrem vazias) e na busca por nome com resultado em uma página só (a página 2 lista clientes que não correspondem à busca). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                         |
| ------------------------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                                  |
| 2. Abrir "Clientes" (`/clientes`) mantendo o Status "Ativo". |
| 3. Olhar a tabela e a paginação abaixo dela.                 |

|                       **Comportamento Esperado**                       |                                                                           **Comportamento Obtido**                                                                            |
| :--------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| A paginação deve oferecer só as páginas que têm clientes (uma página). | A tabela mostra 1 cliente (408 - Lila) e o card "Clientes Ativos" mostra 1, mas a paginação mostra "Anterior 1 2 3 Próxima". Com Status "Todos", a lista mostra 122 clientes. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**           |
| :------------------------: | :-----------------------------------------------: |
|    Clientes / Paginação    | C04-CT05: Listar clientes e conferir a paginação. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:16](https://jam.dev/c/2359f24c-548d-4136-b968-1234c3f2770e) |

---

### 🐞 **Bug 17: Campo Código da busca de clientes aceita letras**

| **ID**  | **Descrição**                                                                     |
| ------- | --------------------------------------------------------------------------------- |
| BUG-017 | O campo Código da busca de clientes aceita letras, embora o código seja numérico. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Entrar no Sifit Unialfa.          |
| 2. Abrir "Clientes" (`/clientes`).   |
| 3. Digitar "abc" no campo Código.    |

|    **Comportamento Esperado**    |   **Comportamento Obtido**    |
| :------------------------------: | :---------------------------: |
| O campo deve aceitar só números. | O campo mantém o texto "abc". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada**  |       **Caso de Teste Relacionado**       |
| :-------------------------: | :---------------------------------------: |
| Clientes / Busca por código | C04-CT16: Digitar letras no campo Código. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:17](coloque o link do video aqui) |

---

### 🐞 **Bug 18: Matrículas ativas pertencem a clientes inativos**

| **ID**  | **Descrição**                                                                                                                                                           |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-018 | A tela de Matrículas mostra 3 matrículas ativas, mas a tela de Clientes mostra só 1 cliente ativo. Os clientes das outras duas matrículas ativas aparecem como INATIVO. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                           |
| ------------------------------------------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                                                    |
| 2. Abrir "Matrículas" (`/matriculas`) e anotar as matrículas com status ATIVO. |
| 3. Abrir "Clientes" (`/clientes`) com Status "Ativo" e depois com "Todos".     |
| 4. Procurar os nomes das matrículas ativas.                                    |

|                                                      **Comportamento Esperado**                                                       |                                                                                                                  **Comportamento Obtido**                                                                                                                  |
| :-----------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Cada matrícula ativa deve pertencer a um cliente ativo, e a quantidade de clientes ativos deve ser coerente com as matrículas ativas. | Matrículas ativas: 242 (Marcelo Longo Zandonadi), 241 (Rafaela Andrade) e 240 (Lila). Clientes ativos: apenas 408 (Lila). Os cadastros de Marcelo Longo Zandonadi e Rafaela Andrade aparecem como INATIVO. A Página Inicial também mostra 1 cliente ativo. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |                **Caso de Teste Relacionado**                 |
| :------------------------: | :----------------------------------------------------------: |
|   Matrículas / Clientes    | C06-CT14: Conferir matrículas ativas com os clientes ativos. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:18](coloque o link do video aqui) |

---

### 🐞 **Bug 19: Totais de Contas a Receber não fecham com a listagem**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-019 | No período do mês, "Entradas" mostra R$ 499,50 (soma das linhas), mas "Recebido no Mês" mostra R$ 475,00 com "100,00% recebido". A conta 1608 tem valor recebido maior que o valor a receber. "Previsto para o Mês" e "Pendentes no Mês" também não consideram as contas pendentes do mês. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                   |
| ---------------------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                                            |
| 2. Abrir "Contas a Receber" (`/contas-receber`) com o período do mês.  |
| 3. Somar a coluna "Valor recebido" das linhas.                         |
| 4. Comparar com "Entradas", "Previsto para o Mês" e "Recebido no Mês". |

|                                            **Comportamento Esperado**                                             |                                                                                   **Comportamento Obtido**                                                                                    |
| :---------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Os totais devem bater com as linhas, e um valor recebido acima do valor a receber deve ser explicado ou impedido. | As seis linhas somam R$ 499,50 (igual a "Entradas"). "Previsto para o Mês" e "Recebido no Mês" mostram R$ 475,00. A conta 1608 (Lila, Matrícula) tem R$ 75,50 a receber e R$ 100,00 recebido. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |        **Caso de Teste Relacionado**         |
| :------------------------: | :------------------------------------------: |
| Contas a Receber / Totais  | C07-CT13: Conferir os totais com a listagem. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:19](https://jam.dev/c/d2060185-943a-429b-bb7f-786c1bcd6119) |

---

### 🐞 **Bug 20: Erro no servidor ao salvar conta a pagar com campos vazios**

| **ID**  | **Descrição**                                                                                                                                                                            |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-020 | Ao salvar uma nova conta a pagar sem preencher nada, a tela mostra apenas "Erro ao salvar conta a pagar", sem dizer o que falta. O mesmo acontece ao salvar sem fornecedor ou sem valor. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                  |
| 2. Abrir "Contas a Pagar" (`/contas-pagar`). |
| 3. Clicar em "Nova Conta".                   |
| 4. Sem preencher nada, clicar em salvar.     |

|                           **Comportamento Esperado**                            |                       **Comportamento Obtido**                       |
| :-----------------------------------------------------------------------------: | :------------------------------------------------------------------: |
| O sistema deve informar quais campos obrigatórios faltam, sem erro de servidor. | A tela mostra "Erro ao salvar conta a pagar", sem dizer o que falta. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada**  |          **Caso de Teste Relacionado**           |
| :-------------------------: | :----------------------------------------------: |
| Contas a Pagar / Nova conta | C13-CT05: Criar conta a pagar com campos vazios. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:20](coloque o link do video aqui) |

---

### 🐞 **Bug 21: Erro no servidor ao abrir caixa com campos vazios**

| **ID**  | **Descrição**                                                                                                                                                                |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-021 | Ao tentar abrir um caixa sem preencher nada, a tela mostra "Erro no servidor. Erro interno inesperado.". O erro também aparece quando só o local de contas fica sem seleção. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                  |
| 2. Abrir "Caixas" (`/caixas`).               |
| 3. Clicar em "Abrir Caixa".                  |
| 4. Sem preencher nada, confirmar a abertura. |

|                     **Comportamento Esperado**                     |                               **Comportamento Obtido**                               |
| :----------------------------------------------------------------: | :----------------------------------------------------------------------------------: |
| O sistema deve informar quais campos faltam, sem erro de servidor. | A tela mostra "Erro no servidor. Erro interno inesperado." e não indica o que falta. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |      **Caso de Teste Relacionado**       |
| :------------------------: | :--------------------------------------: |
|    Caixas / Abrir caixa    | C12-CT06: Abrir caixa com campos vazios. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:21](https://jam.dev/c/00e2006c-624e-4e78-8105-99f9377c84b0) |

---

### 🐞 **Bug 22: Check-ins do dia não batem com a lista de check-ins**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-022 | O card "Check-ins hoje" mostra 3 e "18% vs ontem", mas a tabela está vazia, "Presentes agora" é 0 e a meta do dia está em 0%. A comparação "18% vs ontem" aparece mesmo com 0 check-ins no dia e não muda depois de novos check-ins. Com 1 check-in e 4 clientes ativos, a "Taxa de frequência" mostra 100% em vez de 25%. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                     |
| ------------------------------------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                                              |
| 2. Abrir "Check-in" (`/checkin`).                                        |
| 3. Olhar o card "Check-ins hoje", "Meta do dia" e a tabela de check-ins. |

|                                                **Comportamento Esperado**                                                |                                                                                           **Comportamento Obtido**                                                                                           |
| :----------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| A quantidade de check-ins do dia deve ser a mesma nos indicadores e na tabela, e a meta deve considerar esses check-ins. | Em 28/10/2026: "3 Check-ins hoje", "18% vs ontem", "Presentes agora 0", "0% da meta" (meta 100) e a tabela mostra "Nenhum registro encontrado". Em "Presenças" também aparece "Nenhuma presença encontrada". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |               **Caso de Teste Relacionado**                |
| :------------------------: | :--------------------------------------------------------: |
|   Check-in / Indicadores   | C09-CT09: Conferir os indicadores do Check-in com a lista. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:22](coloque o link do video aqui) |

---

### 🐞 **Bug 23: Horário de pico diferente entre Página Inicial e Check-in**

| **ID**  | **Descrição**                                                                                         |
| ------- | ----------------------------------------------------------------------------------------------------- |
| BUG-023 | A Página Inicial mostra o pico de movimento em "00h - 01h", e a tela de Check-in mostra "18h às 20h". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa e olhar o card "Pico de movimento" da Página Inicial. |
| 2. Abrir "Check-in" (`/checkin`) e olhar "Pico de movimento".                    |

|             **Comportamento Esperado**             |                             **Comportamento Obtido**                             |
| :------------------------------------------------: | :------------------------------------------------------------------------------: |
| O horário de pico deve ser o mesmo nas duas telas. | Página Inicial: "00h - 01h". Check-in: "Horário de maior movimento: 18h às 20h". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|          **Funcionalidade Afetada**           |            **Caso de Teste Relacionado**             |
| :-------------------------------------------: | :--------------------------------------------------: |
| Página inicial / Check-in / Pico de movimento | C09-CT12: Conferir o horário de pico entre as telas. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:23](coloque o link do video aqui) |

---

### 🐞 **Bug 24: Erro no servidor ao salvar colaborador com campos vazios**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                    |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-024 | Ao salvar um novo colaborador sem preencher nada, a tela mostra "Erro no servidor. Erro interno inesperado.". Os campos "Status" e "Sexo" mostram "Ativo" e "Masculino", mas sem valor selecionado: salvar sem alterá-los, mesmo com os demais dados válidos, também gera esse erro. O cadastro só funciona quando Status e Sexo são escolhidos. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                  |
| 2. Abrir "Colaboradores" (`/colaboradores`). |
| 3. Clicar em "Novo Colaborador".             |
| 4. Sem preencher nada, clicar em "Salvar".   |

|                           **Comportamento Esperado**                            |                                    **Comportamento Obtido**                                     |
| :-----------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| O sistema deve informar quais campos obrigatórios faltam, sem erro de servidor. | A tela mostra "Erro no servidor. Erro interno inesperado." e não indica os campos obrigatórios. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |                                          **Caso de Teste Relacionado**                                          |
| :------------------------: | :-------------------------------------------------------------------------------------------------------------: |
|  Colaboradores / Cadastro  | C16-CT04: Cadastrar colaborador com campos vazios. C16-CT06: Cadastro de colaborador sem alterar Status e Sexo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:24](https://jam.dev/c/fa03cb2a-8ed4-45cf-a70a-6a8a999ab4da) |
  [BUG:24](https://jam.dev/c/4e8caa28-0972-44c6-b4e8-34fb85ac989d) |

---

### 🐞 **Bug 25: Cadastro de Planos não avisa nada ao salvar vazio**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-025 | Ao clicar em "Salvar Plano" com o formulário vazio, o sistema não mostra nenhuma mensagem e o cadastro não é salvo. Este registro está em revisão: veio de uma execução automatizada em 28/10/2026, sem vídeo, e em outras execuções o navegador mostrou o aviso "Preencha este campo." ao salvar o mesmo formulário vazio. Se o vídeo do roteiro mostrar o aviso, o bug deve ser cancelado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            | Em revisão |

| **Passo a passo para simular o bug**             |
| ------------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                      |
| 2. Abrir "Planos" (`/planos`).                   |
| 3. Clicar em "Novo Plano".                       |
| 4. Sem preencher nada, clicar em "Salvar Plano". |

|               **Comportamento Esperado**               |                                   **Comportamento Obtido**                                    |
| :----------------------------------------------------: | :-------------------------------------------------------------------------------------------: |
| O sistema deve informar o campo obrigatório que falta. | Nada acontece e nenhuma mensagem aparece. A pessoa não sabe por que o cadastro não foi salvo. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**            |
| :------------------------: | :-------------------------------------------------: |
|     Planos / Cadastro      | C05-CT12: Cadastro de plano com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:25](coloque o link do video aqui) |

---

### 🐞 **Bug 26: Cadastro de Prospecção não avisa nada ao salvar vazio**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                               |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-026 | Ao clicar em "Salvar Lead" com o formulário vazio, o sistema não mostra nenhuma mensagem e o cadastro não é salvo. Este registro está em revisão: veio de uma execução automatizada em 28/10/2026, sem vídeo, e em outras execuções o navegador mostrou o aviso "Preencha este campo." ao salvar o mesmo formulário vazio. Se o vídeo do roteiro mostrar o aviso, o bug deve ser cancelado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            | Em revisão |

| **Passo a passo para simular o bug**            |
| ----------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                     |
| 2. Abrir "Prospecção" (`/prospeccao`).          |
| 3. Clicar em "Adicionar Lead".                  |
| 4. Sem preencher nada, clicar em "Salvar Lead". |

|               **Comportamento Esperado**               |                                   **Comportamento Obtido**                                    |
| :----------------------------------------------------: | :-------------------------------------------------------------------------------------------: |
| O sistema deve informar o campo obrigatório que falta. | Nada acontece e nenhuma mensagem aparece. A pessoa não sabe por que o cadastro não foi salvo. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |    **Caso de Teste Relacionado**     |
| :------------------------: | :----------------------------------: |
|   Prospecção / Cadastro    | C15-CT07: Cadastro de lead sem nome. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:26](coloque o link do video aqui) |

---

### 🐞 **Bug 27: Erro genérico ao salvar produto vazio**

| **ID**  | **Descrição**                                                                                         |
| ------- | ----------------------------------------------------------------------------------------------------- |
| BUG-027 | Ao salvar um produto vazio, a tela mostra só "Erro ao salvar produto", sem indicar o campo que falta. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**       |
| ------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                |
| 2. Abrir "Produtos" (`/produtos`).         |
| 3. Clicar em "Novo".                       |
| 4. Sem preencher nada, clicar em "Salvar". |

|               **Comportamento Esperado**               |          **Comportamento Obtido**          |
| :----------------------------------------------------: | :----------------------------------------: |
| O sistema deve informar o campo obrigatório que falta. | A tela mostra só "Erro ao salvar produto". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**           |
| :------------------------: | :-----------------------------------------------: |
|    Produtos / Cadastro     | C17-CT04: Salvar Produtos com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:27](coloque o link do video aqui) |

---

### 🐞 **Bug 28: Erro genérico ao salvar enquete vazia**

| **ID**  | **Descrição**                                                                                 |
| ------- | --------------------------------------------------------------------------------------------- |
| BUG-028 | Ao salvar uma enquete vazia, a tela mostra "Erro ao salvar enquete", sem indicar o que falta. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**       |
| ------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                |
| 2. Abrir "Enquetes" (`/enquetes`).         |
| 3. Clicar em "Nova Enquete".               |
| 4. Sem preencher nada, clicar em "Salvar". |

|               **Comportamento Esperado**               |                     **Comportamento Obtido**                     |
| :----------------------------------------------------: | :--------------------------------------------------------------: |
| O sistema deve informar o campo obrigatório que falta. | A tela mostra "Erro ao salvar enquete", sem indicar o que falta. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**           |
| :------------------------: | :-----------------------------------------------: |
|    Enquetes / Cadastro     | C19-CT03: Salvar Enquetes com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:28](coloque o link do video aqui) |

---

### 🐞 **Bug 29: Atividades permite salvar registro em branco**

| **ID**  | **Descrição**                                                                             |
| ------- | ----------------------------------------------------------------------------------------- |
| BUG-029 | Ao salvar o formulário de Atividades vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**       |
| ------------------------------------------ |
| 1. Entrar no Sifit Unialfa.                |
| 2. Abrir "Atividades" (`/atividades`).     |
| 3. Clicar em "Nova Atividade".             |
| 4. Sem preencher nada, clicar em "Salvar". |
| 5. Olhar a lista.                          |

|              **Comportamento Esperado**              |                                                     **Comportamento Obtido**                                                     |
| :--------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve exigir o nome e não criar o registro. | O formulário vazio é salvo e a lista passa de 4 para 5 registros, com a linha 5 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**            |
| :------------------------: | :-------------------------------------------------: |
|   Atividades / Cadastro    | C19-CT04: Salvar Atividades com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:29](coloque o link do video aqui) |

---

### 🐞 **Bug 30: Objetivos de Treino permite salvar registro em branco**

| **ID**  | **Descrição**                                                                                      |
| ------- | -------------------------------------------------------------------------------------------------- |
| BUG-030 | Ao salvar o formulário de Objetivos de Treino vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                  |
| ----------------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                           |
| 2. Abrir "Objetivos de Treino" (`/objetivos-treino`). |
| 3. Clicar em "Novo Objetivo".                         |
| 4. Sem preencher nada, clicar em "Salvar".            |
| 5. Olhar a lista.                                     |

|              **Comportamento Esperado**              |                                                    **Comportamento Obtido**                                                     |
| :--------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve exigir o nome e não criar o registro. | O formulário vazio é salvo e a lista passa de 0 para 1 registro, com a linha 1 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|   **Funcionalidade Afetada**   |                **Caso de Teste Relacionado**                 |
| :----------------------------: | :----------------------------------------------------------: |
| Objetivos de Treino / Cadastro | C19-CT07: Salvar Objetivos de Treino com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:30](coloque o link do video aqui) |

---

### 🐞 **Bug 31: Tipos de Pagamento permite salvar registro em branco**

| **ID**  | **Descrição**                                                                                     |
| ------- | ------------------------------------------------------------------------------------------------- |
| BUG-031 | Ao salvar o formulário de Tipos de Pagamento vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                |
| --------------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                         |
| 2. Abrir "Tipos de Pagamento" (`/tipos-pagamento`). |
| 3. Clicar em "Novo".                                |
| 4. Sem preencher nada, clicar em "Salvar".          |
| 5. Olhar a lista.                                   |

|              **Comportamento Esperado**              |                                                      **Comportamento Obtido**                                                       |
| :--------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve exigir o nome e não criar o registro. | O formulário vazio é salvo e a lista passa de 10 para 11 registros, com a linha 12 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|  **Funcionalidade Afetada**   |                **Caso de Teste Relacionado**                |
| :---------------------------: | :---------------------------------------------------------: |
| Tipos de Pagamento / Cadastro | C19-CT08: Salvar Tipos de Pagamento com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:31](coloque o link do video aqui) |

---

### 🐞 **Bug 32: Erro ao salvar pergunta de anamnese vazia**

| **ID**  | **Descrição**                                                                                                  |
| ------- | -------------------------------------------------------------------------------------------------------------- |
| BUG-032 | Ao salvar uma pergunta de anamnese vazia, a tela mostra só "Erro ao salvar pergunta", sem indicar o que falta. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                      |
| --------------------------------------------------------- |
| 1. Entrar no Sifit Unialfa.                               |
| 2. Abrir "Perguntas" de Anamnese (`/perguntas-anamnese`). |
| 3. Clicar em "Nova Pergunta".                             |
| 4. Sem preencher nada, clicar em "Salvar".                |

|                          **Comportamento Esperado**                          |          **Comportamento Obtido**           |
| :--------------------------------------------------------------------------: | :-----------------------------------------: |
| O sistema deve informar o campo obrigatório que falta, sem erro de servidor. | A tela mostra só "Erro ao salvar pergunta". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 28/10/2026                         |

|    **Funcionalidade Afetada**    |                 **Caso de Teste Relacionado**                  |
| :------------------------------: | :------------------------------------------------------------: |
| Perguntas de Anamnese / Cadastro | C19-CT09: Salvar Perguntas de Anamnese com o formulário vazio. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:32](coloque o link do video aqui) |

---

### 🐞 **Bug 33: Quantidade de clientes ausentes diverge entre a Página Inicial e a tela de Clientes**

| **ID**  | **Descrição**                                                                                                                                                                               |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-033 | A Página Inicial exibe 4 clientes ausentes (Rafael Santos, Jerome Lionel, Steven Kaiki e Lila, todos sem visitas registradas), enquanto o indicador "Ausentes" da tela de Clientes exibe 0. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**    |
| --------------------------------------- |
| 1. Acessar a Página Inicial do SIFIT.   |
| 2. Observar o card "Clientes Ausentes". |
| 3. Acessar a tela de Clientes.          |
| 4. Observar o indicador "Ausentes".     |

|                     **Comportamento Esperado**                      |                **Comportamento Obtido**                |
| :-----------------------------------------------------------------: | :----------------------------------------------------: |
| As duas telas devem exibir a mesma quantidade de clientes ausentes. | A Página Inicial exibe 4 e a tela de Clientes exibe 0. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Página Inicial / Clientes  | C02-CT03: Clientes ausentes.  |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:33](https://jam.dev/c/7cde0ad8-fe3a-4a3b-9a14-0805dca3875b) |

---

### 🐞 **Bug 34: Lista de desistências vazia, embora o total informe 3 desistências**

| **ID**  | **Descrição**                                                                                                                                                                |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-034 | Ao clicar no card "Desistências no Período", que exibe 3, a janela exibe a mensagem "Nenhuma desistência encontrada no período." e, logo abaixo, "Total de desistências: 3". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**          |
| --------------------------------------------- |
| 1. Acessar a Página Inicial do SIFIT.         |
| 2. Observar o card "Desistências no Período". |
| 3. Clicar no card.                            |
| 4. Verificar a lista e o total exibidos.      |

|             **Comportamento Esperado**             |                     **Comportamento Obtido**                      |
| :------------------------------------------------: | :---------------------------------------------------------------: |
| A janela deve listar as 3 desistências do período. | A janela informa que não há desistências, mas exibe o total de 3. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**   |   **Caso de Teste Relacionado**    |
| :---------------------------: | :--------------------------------: |
| Página Inicial / Desistências | C02-CT05: Desistências no período. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:34](https://jam.dev/c/9b8a90d6-7d67-426f-8c6b-48eb4b8e1296) |

---

### 🐞 **Bug 35: Erro ao cadastrar cliente com dados válidos**

| **ID**  | **Descrição**                                                                                                                                                                                          |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-035 | Ao preencher todos os campos obrigatórios (e também os opcionais) com dados válidos e clicar em "Cadastrar Cliente", o sistema exibe a mensagem "Erro ao criar cliente." e o cliente não é cadastrado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|        Crítica        |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                          |
| --------------------------------------------------------------------------------------------- |
| 1. Acessar a tela de clientes do SIFIT.                                                       |
| 2. Clicar no botão "Novo Cliente".                                                            |
| 3. Preencher Nome ("Teste Ville Nunes"), Status ("Ativo"), Sexo e Data de Nascimento válidos. |
| 4. Clicar no botão "Cadastrar Cliente".                                                       |
| 5. Verificar a mensagem exibida pelo sistema.                                                 |

|                                 **Comportamento Esperado**                                 |                               **Comportamento Obtido**                                |
| :----------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------: |
| O sistema deve cadastrar o cliente, exibir mensagem de sucesso e apresentá-lo na listagem. | O sistema exibe o modal "Erro - Erro ao criar cliente." e o cliente não é cadastrado. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |          **Caso de Teste Relacionado**           |
| :----------------------------: | :----------------------------------------------: |
| Clientes / Cadastro de cliente | C04-CT08: Cadastro de cliente com dados válidos. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:35](https://jam.dev/c/e21003f6-a3e5-4f6f-9ea2-755f25b7ff91) |

---

### 🐞 **Bug 36: Busca por código não retorna clientes sem matrícula**

| **ID**  | **Descrição**                                                                                                                                                                                                               |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-036 | Ao pesquisar pelo código de um cliente que não possui matrícula (ex.: 406 e 408), a listagem retorna vazia, embora o cliente exista e apareça na listagem padrão. Para clientes com matrícula (ex.: 398), a busca funciona. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**          |
| --------------------------------------------- |
| 1. Acessar a tela de clientes do SIFIT.       |
| 2. Informar o código "408" no campo "Código". |
| 3. Clicar no botão "Buscar".                  |
| 4. Verificar a listagem exibida.              |

|                   **Comportamento Esperado**                   |                                               **Comportamento Obtido**                                                |
| :------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------: |
| O sistema deve exibir o cliente que possui o código informado. | A tela de clientes fica totalmente em branco após clicar em "Buscar", embora o cliente 408 esteja cadastrado e ativo. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  |     **Caso de Teste Relacionado**     |
| :-------------------------: | :-----------------------------------: |
| Clientes / Busca por código | C04-CT04: Buscar cliente pelo código. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:36](https://jam.dev/c/e36fb928-6b21-4210-b361-cc99a1358cf9) |

---

### 🐞 **Bug 37: Listagem não respeita a quantidade de registros por página**

| **ID**  | **Descrição**                                                                                                                                                                       |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-037 | Com a opção "50" registros por página selecionada e o filtro "Status" em "Todos", a primeira página exibe todos os 126 clientes cadastrados, enquanto a página 2 exibe 50 clientes. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                            |
| --------------------------------------------------------------- |
| 1. Acessar a tela de clientes do SIFIT.                         |
| 2. Selecionar "Todos" no filtro "Status".                       |
| 3. Clicar no botão "Buscar".                                    |
| 4. Contar a quantidade de clientes exibidos na primeira página. |

|              **Comportamento Esperado**              |                              **Comportamento Obtido**                               |
| :--------------------------------------------------: | :---------------------------------------------------------------------------------: |
| A primeira página deve exibir no máximo 50 clientes. | A primeira página exibe todos os clientes cadastrados (125 no momento da gravação). |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |         **Caso de Teste Relacionado**         |
| :------------------------: | :-------------------------------------------: |
|    Clientes / Paginação    | C04-CT06: Quantidade de registros por página. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:37](https://jam.dev/c/7e9313e8-1a42-4e1f-99be-f22711d0d555) |

---

### 🐞 **Bug 38: Ausência de mensagem quando a busca não encontra clientes**

| **ID**  | **Descrição**                                                                                                                                           |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-038 | Ao pesquisar um nome que não está cadastrado, o sistema exibe apenas a tabela vazia, sem nenhuma mensagem informando que nenhum cliente foi encontrado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**             |
| ------------------------------------------------ |
| 1. Acessar a tela de clientes do SIFIT.          |
| 2. Informar um nome inexistente no campo "Nome". |
| 3. Clicar no botão "Buscar".                     |
| 4. Verificar a listagem exibida.                 |

|                      **Comportamento Esperado**                      |                           **Comportamento Obtido**                           |
| :------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| O sistema deve exibir uma mensagem como "Nenhum cliente encontrado". | O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |          **Caso de Teste Relacionado**           |
| :------------------------: | :----------------------------------------------: |
| Clientes / Busca por nome  | C04-CT03: Busca de cliente com nome inexistente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:38](https://jam.dev/c/1400615a-e41d-4ab8-95d5-5a68bd56510d) |

---

### 🐞 **Bug 39: Erro ao salvar alterações dos dados do cliente**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-039 | Ao alterar os dados de um cliente existente (ex.: nome ou status) e clicar em "Salvar Alterações", o sistema exibe a mensagem "Erro ao criar cliente." e as alterações não são salvas. Além disso, a mensagem exibida menciona "criar" em uma operação de alteração. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|        Crítica        |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                   |
| ---------------------------------------------------------------------- |
| 1. Acessar a tela de clientes do SIFIT.                                |
| 2. Clicar no botão "Visualizar" de um cliente (ex.: código 405).       |
| 3. Clicar no botão "Alterar dados".                                    |
| 4. Alterar o nome para "Teste Ville Nunes" ou o status para "Inativo". |
| 5. Clicar no botão "Salvar Alterações".                                |

|                                           **Comportamento Esperado**                                           |                                        **Comportamento Obtido**                                        |
| :------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------: |
| O sistema deve salvar as alterações, exibir mensagem de sucesso e apresentar os dados atualizados na listagem. | O sistema exibe o modal "Erro - Erro ao criar cliente." e o cliente permanece com os dados anteriores. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|          **Funcionalidade Afetada**          |       **Caso de Teste Relacionado**       |
| :------------------------------------------: | :---------------------------------------: |
| Clientes / Alteração e inativação de cliente | C04-CT10: Alteração dos dados do cliente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:39](https://jam.dev/c/ef0c7a28-0a2f-4bb6-9c78-3fc0995ec51f) |

---

### 🐞 **Bug 40: Erro no servidor ao acessar cliente excluído**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-040 | Ao acessar pela URL a tela de visualização ou alteração de um cliente que foi excluído (ex.: /visualizar-cliente/407), o sistema exibe o modal "Erro no servidor - Erro interno inesperado." e, na tela de alteração, carrega o formulário vazio com o botão "Cadastrar Cliente". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                         |
| ------------------------------------------------------------ |
| 1. Acessar o SIFIT autenticado.                              |
| 2. Acessar a URL /visualizar-cliente/407 (cliente excluído). |
| 3. Verificar a mensagem exibida pelo sistema.                |

|                                      **Comportamento Esperado**                                      |                    **Comportamento Obtido**                    |
| :--------------------------------------------------------------------------------------------------: | :------------------------------------------------------------: |
| O sistema deve informar que o cliente não foi encontrado e redirecionar para a listagem de clientes. | O sistema exibe "Erro no servidor - Erro interno inesperado.". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|     **Funcionalidade Afetada**     |        **Caso de Teste Relacionado**         |
| :--------------------------------: | :------------------------------------------: |
| Clientes / Visualização de cliente | C04-CT09: Visualização dos dados do cliente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:40](https://jam.dev/c/132ddc8a-ed22-488c-9527-d95562c4b9d8) |

---

### 🐞 **Bug 41: Coluna "Alunos", ranking e receita estimada dos planos exibem valores zerados**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-041 | Na tela de planos, a coluna "Alunos" exibe 0 para todos os planos e o indicador "Receita Estimada" exibe R$ 0,00, embora o indicador "Alunos em Planos" mostre 2 e o ranking mostre o plano "Treino Livre" com 1 aluno. No ranking, a mensalidade do "Treino Livre" é exibida como R$ 0,00, embora o plano custe R$ 52,00. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Acessar a tela de planos do SIFIT.                                            |
| 2. Observar o indicador "Alunos em Planos" e o ranking "Planos com mais alunos". |
| 3. Observar a coluna "Alunos" do plano "Treino Livre" na listagem.               |
| 4. Observar o indicador "Receita Estimada".                                      |

|                                                          **Comportamento Esperado**                                                           |                                       **Comportamento Obtido**                                        |
| :-------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| A coluna "Alunos", o ranking e a receita estimada devem refletir as matrículas ativas (ex.: Treino Livre com 1 aluno e mensalidade R$ 52,00). | A coluna "Alunos" exibe 0, a receita estimada exibe R$ 0,00 e a mensalidade no ranking exibe R$ 0,00. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**    |                    **Caso de Teste Relacionado**                    |
| :-----------------------------: | :-----------------------------------------------------------------: |
| Planos / Listagem e indicadores | C05-CT02: Exibição da quantidade de alunos e da receita dos planos. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:41](https://jam.dev/c/a5ed20f9-d1e4-4e37-90ce-9941e6799792) |

---

### 🐞 **Bug 42: Busca por código retorna planos cujo código apenas contém o valor informado**

| **ID**  | **Descrição**                                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-042 | Ao pesquisar o código "1", a listagem retorna os planos #1, #11, #16, #41 e #51, ou seja, todos os planos cujo código contém o dígito "1", em vez de somente o plano #1. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**  |
| ------------------------------------- |
| 1. Acessar a tela de planos do SIFIT. |
| 2. Informar "1" no campo "Código".    |
| 3. Clicar no botão "Buscar".          |
| 4. Verificar os planos exibidos.      |

|             **Comportamento Esperado**              |              **Comportamento Obtido**              |
| :-------------------------------------------------: | :------------------------------------------------: |
| O sistema deve exibir somente o plano de código #1. | O sistema exibe os planos #1, #11, #16, #41 e #51. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |     **Caso de Teste Relacionado**     |
| :------------------------: | :-----------------------------------: |
| Planos / Busca por código  | C05-CT04: Busca de plano pelo código. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:42](https://jam.dev/c/ec3ca053-5d62-438d-aa52-034d12e49b9a) |

---

### 🐞 **Bug 43: Erro interno com exposição de SQL ao salvar plano sem grupo**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-043 | Ao salvar um plano informando apenas o nome, o sistema exibe a mensagem genérica "Erro ao salvar plano". No DevTools (aba Network), a resposta mostra uma mensagem do banco de dados dizendo que o grupo não pode ficar vazio. Ou seja, o campo "Grupo" não é validado e o sistema expõe detalhes internos. O campo Grupo não tem opção selecionada nem indicação de obrigatório. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                 |
| ------------------------------------------------------------------------------------ |
| 1. Acessar a tela de planos do SIFIT.                                                |
| 2. Clicar no botão "Novo Plano".                                                     |
| 3. Informar apenas o nome "Plano Teste Ville".                                       |
| 4. Clicar no botão "Salvar Plano".                                                   |
| 5. Verificar a mensagem exibida e, no DevTools (aba Network), a resposta do sistema. |

|                                             **Comportamento Esperado**                                              |                                       **Comportamento Obtido**                                        |
| :-----------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| O sistema deve informar que o campo "Grupo" é obrigatório, sem erro interno e sem expor detalhes do banco de dados. | A tela mostra só "Erro ao salvar plano". No DevTools, a resposta mostra a mensagem do banco de dados. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |     **Caso de Teste Relacionado**      |
| :------------------------: | :------------------------------------: |
| Planos / Cadastro de plano | C05-CT05: Cadastro de plano sem grupo. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:43](https://jam.dev/c/fa85a065-f8b6-45aa-989b-d65a05e2eb66) |

---

### 🐞 **Bug 44: Sistema permite cadastrar plano com quantidade de parcelas negativa**

| **ID**  | **Descrição**                                                                                |
| ------- | -------------------------------------------------------------------------------------------- |
| BUG-044 | O campo "Parcelas" aceita valores negativos e o plano é salvo normalmente com "-3" parcelas. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                        |
| ----------------------------------------------------------- |
| 1. Acessar a tela de planos do SIFIT.                       |
| 2. Clicar no botão "Novo Plano".                            |
| 3. Informar o nome "Plano Teste Ville Negativo" e um grupo. |
| 4. Informar "-3" no campo "Parcelas".                       |
| 5. Clicar no botão "Salvar Plano".                          |

|                                     **Comportamento Esperado**                                     |        **Comportamento Obtido**         |
| :------------------------------------------------------------------------------------------------: | :-------------------------------------: |
| O sistema deve impedir o cadastro e informar que a quantidade de parcelas deve ser maior que zero. | O plano é cadastrado com "-3" parcelas. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |                  **Caso de Teste Relacionado**                   |
| :------------------------: | :--------------------------------------------------------------: |
| Planos / Cadastro de plano | C05-CT06: Cadastro de plano com quantidade de parcelas negativa. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:44](https://jam.dev/c/1a785e1d-5f84-4b11-9c13-50be1961a7f4) |

---

### 🐞 **Bug 45: Inativação do plano não é salva**

| **ID**  | **Descrição**                                                                                                                                                                                   |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-045 | Ao alterar o status de um plano para "Inativo" e clicar em "Salvar Plano", o plano permanece "ATIVO" na listagem e ao ser reaberto. As demais alterações (nome e valor) são salvas normalmente. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                  |
| ------------------------------------------------------------------------------------- |
| 1. Acessar a tela de planos do SIFIT.                                                 |
| 2. Clicar no botão "Visualizar" de um plano ativo (ex.: "Plano Teste Ville Editado"). |
| 3. Selecionar "Inativo" no campo "Status".                                            |
| 4. Clicar no botão "Salvar Plano".                                                    |
| 5. Verificar o status do plano na listagem.                                           |

|         **Comportamento Esperado**         |       **Comportamento Obtido**        |
| :----------------------------------------: | :-----------------------------------: |
| O plano deve constar com status "INATIVO". | O plano permanece com status "ATIVO". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  | **Caso de Teste Relacionado**  |
| :-------------------------: | :----------------------------: |
| Planos / Alteração de plano | C05-CT09: Inativação do plano. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:45](https://jam.dev/c/9f76f60c-600d-4c55-b9ae-8eb8069889e9) |

---

### 🐞 **Bug 46: Planos inativos são exibidos no cadastro de matrícula**

| **ID**  | **Descrição**                                                                                                                                                                                     |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-046 | No campo "Modalidade" da tela "Cadastrar Matrícula", são exibidos planos com status "INATIVO" (ex.: "AVA" e "Teste Final"), permitindo matricular clientes em planos que não estão mais em vigor. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Acessar a tela de planos do SIFIT e identificar planos inativos (ex.: "AVA"). |
| 2. Acessar a tela "Cadastrar Matrícula".                                         |
| 3. Abrir o campo "Modalidade".                                                   |
| 4. Verificar se os planos inativos são exibidos.                                 |

|                   **Comportamento Esperado**                    |                     **Comportamento Obtido**                      |
| :-------------------------------------------------------------: | :---------------------------------------------------------------: |
| Somente planos ativos devem ser exibidos no campo "Modalidade". | Os planos inativos "AVA" e "Teste Final" são exibidos como opção. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**             |
| :------------------------: | :--------------------------------------------------: |
|    Planos / Matrículas     | C05-CT10: Plano inativo indisponível para matrícula. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:46](https://jam.dev/c/96013002-d0e4-4057-8dc1-383ef6437707) |

---

### 🐞 **Bug 47: Desconto não é aplicado ao valor total da matrícula**

| **ID**  | **Descrição**                                                                                                                                                                                                                                    |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-047 | Ao informar um desconto no cadastro da matrícula, o campo "Valor Total" não é recalculado. Na tela "Visualizar Matrícula", o campo "Desconto" exibe o valor da parcela (R$ 52,00) em vez do desconto informado, inclusive quando o desconto é 0. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                              |
| ----------------------------------------------------------------- |
| 1. Acessar a tela de matrículas do SIFIT.                         |
| 2. Clicar em "Cadastrar Matrícula".                               |
| 3. Selecionar o cliente e a modalidade "Treino Livre" (R$ 52,00). |
| 4. Informar "10" no campo "Desconto" e verificar o "Valor Total". |
| 5. Salvar a matrícula e clicar em "Visualizar" na listagem.       |

|                             **Comportamento Esperado**                             |                         **Comportamento Obtido**                          |
| :--------------------------------------------------------------------------------: | :-----------------------------------------------------------------------: |
| O valor total deve ser R$ 42,00 e a visualização deve exibir desconto de R$ 10,00. | O valor total permanece R$ 52,00 e a visualização exibe "Desconto 52,00". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|      **Funcionalidade Afetada**      |                                **Caso de Teste Relacionado**                                 |
| :----------------------------------: | :------------------------------------------------------------------------------------------: |
| Matrículas / Cadastro e visualização | C06-CT08: Cadastro de matrícula com desconto. C06-CT10: Visualização dos dados da matrícula. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:47](https://jam.dev/c/561a6194-6092-4ce0-a67f-71e0da5a84ca) |

---

### 🐞 **Bug 48: Mensagem incorreta ao cadastrar matrícula para cliente com matrícula ativa**

| **ID**  | **Descrição**                                                                                                                                                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-048 | Ao tentar cadastrar uma matrícula para um cliente que já possui matrícula ativa, o sistema impede o cadastro, porém exibe a mensagem genérica "Erro ao Cadastrar com Assinatura". A tela não informa que o cliente já tem matrícula ativa. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                        |
| --------------------------------------------------------------------------- |
| 1. Acessar a tela "Cadastrar Matrícula" do SIFIT.                           |
| 2. Selecionar um cliente que já possui matrícula ativa (ex.: Steven Kaiki). |
| 3. Preencher modalidade, tipo de pagamento e dia de vencimento.             |
| 4. Clicar no botão "Salvar".                                                |
| 5. Verificar a mensagem exibida pelo sistema.                               |

|                    **Comportamento Esperado**                    |                    **Comportamento Obtido**                    |
| :--------------------------------------------------------------: | :------------------------------------------------------------: |
| O sistema deve informar que o cliente já possui matrícula ativa. | O sistema exibe a mensagem "Erro ao Cadastrar com Assinatura". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|     **Funcionalidade Afetada**     |                   **Caso de Teste Relacionado**                   |
| :--------------------------------: | :---------------------------------------------------------------: |
| Matrículas / Cadastro de matrícula | C06-CT09: Cadastro de matrícula para cliente com matrícula ativa. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:48](https://jam.dev/c/7058b67e-1662-4ab3-9b6c-5bdb8f2c041c) |

---

### 🐞 **Bug 49: Paginação não permite acessar matrículas além da primeira página**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                 |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-049 | Com a opção "50" registros por página, a listagem exibe 50 matrículas e apenas a página "1", com o botão "Próxima" desabilitado. Ao alterar para "100" registros por página, são exibidas 84 matrículas, ou seja, 34 matrículas ficam inacessíveis com a configuração padrão. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                        |
| --------------------------------------------------------------------------- |
| 1. Acessar a tela de matrículas do SIFIT.                                   |
| 2. Manter a opção "50" registros por página.                                |
| 3. Verificar a paginação e o botão "Próxima".                               |
| 4. Alterar para "100" registros por página e contar as matrículas exibidas. |

|                       **Comportamento Esperado**                       |                          **Comportamento Obtido**                           |
| :--------------------------------------------------------------------: | :-------------------------------------------------------------------------: |
| A paginação deve exibir 2 páginas e permitir acessar as 84 matrículas. | A paginação exibe somente a página 1 e o botão "Próxima" fica desabilitado. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |         **Caso de Teste Relacionado**          |
| :------------------------: | :--------------------------------------------: |
|   Matrículas / Paginação   | C06-CT04: Paginação da listagem de matrículas. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:49](https://jam.dev/c/de75bafc-86f6-45f1-9e87-83269324988b) |

---

### 🐞 **Bug 50: Erro no servidor ao excluir matrícula, embora a exclusão seja efetivada**

| **ID**  | **Descrição**                                                                                                                                                                                                                    |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-050 | Ao confirmar a exclusão de uma matrícula, o sistema exibe o modal "Erro no servidor - Erro interno inesperado.", porém a matrícula é removida da listagem. O usuário é informado de uma falha em uma operação que foi realizada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                      |
| --------------------------------------------------------- |
| 1. Acessar a tela de matrículas do SIFIT.                 |
| 2. Clicar no botão "Deletar" (lixeira) de uma matrícula.  |
| 3. Confirmar a mensagem "Deseja deletar essa matrícula?". |
| 4. Verificar a mensagem exibida e a listagem.             |

|                    **Comportamento Esperado**                    |                                                                                   **Comportamento Obtido**                                                                                    |
| :--------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve excluir a matrícula e exibir mensagem de sucesso. | O sistema exibe "Erro no servidor - Erro interno inesperado." e a listagem não é atualizada (a matrícula continua aparecendo até a página ser recarregada), embora a exclusão seja efetivada. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|     **Funcionalidade Afetada**     |  **Caso de Teste Relacionado**   |
| :--------------------------------: | :------------------------------: |
| Matrículas / Exclusão de matrícula | C06-CT12: Exclusão de matrícula. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:50](https://jam.dev/c/21646323-7507-4ece-a3b1-16ab9def23ef) |

---

### 🐞 **Bug 51: Mensagem de validação permanece após selecionar o tipo de pagamento**

| **ID**  | **Descrição**                                                                                                                                                                                      |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-051 | Após tentar salvar a matrícula sem tipo de pagamento, a mensagem "Selecione o Tipo de Pagamento" é exibida abaixo do campo e permanece na tela mesmo depois que o tipo de pagamento é selecionado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                       |
| ---------------------------------------------------------- |
| 1. Acessar a tela "Cadastrar Matrícula" do SIFIT.          |
| 2. Selecionar cliente e modalidade, sem tipo de pagamento. |
| 3. Clicar no botão "Salvar".                               |
| 4. Selecionar um tipo de pagamento (ex.: "Cheque").        |
| 5. Verificar a mensagem abaixo do campo "Tipo Pagamento".  |

|                       **Comportamento Esperado**                        |                   **Comportamento Obtido**                    |
| :---------------------------------------------------------------------: | :-----------------------------------------------------------: |
| A mensagem de validação deve desaparecer quando o campo for preenchido. | A mensagem "Selecione o Tipo de Pagamento" permanece exibida. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|     **Funcionalidade Afetada**     |             **Caso de Teste Relacionado**              |
| :--------------------------------: | :----------------------------------------------------: |
| Matrículas / Cadastro de matrícula | C06-CT06: Cadastro de matrícula sem tipo de pagamento. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:51](https://jam.dev/c/5a82af04-828e-49bb-9853-4e01baa8aa28) |

---

### 🐞 **Bug 52: Ausência de mensagem quando a busca não encontra matrículas**

| **ID**  | **Descrição**                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-052 | Ao pesquisar um nome que não possui matrícula, o sistema exibe apenas a tabela vazia, sem nenhuma mensagem informando que nenhuma matrícula foi encontrada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**             |
| ------------------------------------------------ |
| 1. Acessar a tela de matrículas do SIFIT.        |
| 2. Informar um nome inexistente no campo "Nome". |
| 3. Clicar no botão "Buscar".                     |
| 4. Verificar a listagem exibida.                 |

|                       **Comportamento Esperado**                        |                           **Comportamento Obtido**                           |
| :---------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| O sistema deve exibir uma mensagem como "Nenhuma matrícula encontrada". | O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  |           **Caso de Teste Relacionado**            |
| :-------------------------: | :------------------------------------------------: |
| Matrículas / Busca por nome | C06-CT03: Busca de matrícula com nome inexistente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:52](https://jam.dev/c/d1626ff1-a6d5-43c0-a063-d9127141bb66) |

---

### 🐞 **Bug 53: Campo "Dia Vencimento" aceita data e exibe erro de SQL ao salvar a matrícula**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-053 | O campo "Dia Vencimento" do cadastro de matrícula aceita qualquer texto, como uma data completa ("26/11/2026"). Ao salvar, o sistema exibe a janela "Não foi possível concluir" com uma mensagem do banco de dados ("Data too long for column 'dia_venc_pag'"), sem orientar que o campo deve conter apenas o dia (1 a 31) e expondo detalhes internos do banco. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                                   |
| ------------------------------------------------------------------------------------------------------ |
| 1. Acessar a tela "Cadastrar Matrícula" do SIFIT.                                                      |
| 2. Selecionar um cliente sem matrícula ativa, a modalidade "Treino Livre" e o tipo de pagamento "Pix". |
| 3. Informar "26/11/2026" no campo "Dia Vencimento".                                                    |
| 4. Clicar no botão "Salvar".                                                                           |
| 5. Verificar a mensagem exibida.                                                                       |

|                                                  **Comportamento Esperado**                                                   |                            **Comportamento Obtido**                             |
| :---------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------: |
| O campo deve aceitar apenas números de 1 a 31 e o sistema deve informar o formato correto, sem expor erros do banco de dados. | O sistema exibe "Não foi possível concluir" com uma mensagem do banco de dados. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|     **Funcionalidade Afetada**     |           **Caso de Teste Relacionado**            |
| :--------------------------------: | :------------------------------------------------: |
| Matrículas / Cadastro de matrícula | C06-CT07: Cadastro de matrícula com dados válidos. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:53](https://jam.dev/c/f6c8984a-4de5-4654-86d1-0b7e676b04bc) |

---

### 🐞 **Bug 54: Indicador "Contas Atrasadas" diverge do filtro de contas vencidas**

| **ID**  | **Descrição**                                                                                                      |
| ------- | ------------------------------------------------------------------------------------------------------------------ |
| BUG-054 | O indicador "Contas Atrasadas" exibe 2, porém ao filtrar a listagem pelo status "Vencido" nenhuma conta é exibida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**            |
| ----------------------------------------------- |
| 1. Acessar a tela de contas a receber do SIFIT. |
| 2. Observar o indicador "Contas Atrasadas".     |
| 3. Selecionar "Vencido" no filtro "Status".     |
| 4. Clicar no botão "Buscar".                    |

|                      **Comportamento Esperado**                      |      **Comportamento Obtido**       |
| :------------------------------------------------------------------: | :---------------------------------: |
| A listagem deve exibir as 2 contas atrasadas indicadas no indicador. | A listagem não exibe nenhuma conta. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|        **Funcionalidade Afetada**        |              **Caso de Teste Relacionado**               |
| :--------------------------------------: | :------------------------------------------------------: |
| Contas a Receber / Indicadores e filtros | C07-CT05: Consistência do indicador de contas atrasadas. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:54](https://jam.dev/c/e32d62f2-82da-4f71-b65d-8c9ebfff90c1) |

---

### 🐞 **Bug 55: Recebimento é registrado sem tipo de pagamento**

| **ID**  | **Descrição**                                                                                                                                                                                                                                            |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-055 | Ao efetuar o recebimento de uma conta sem selecionar o tipo de pagamento, o sistema registra o recebimento normalmente. Na visualização da conta, o campo "Tipo de Pagamento" fica vazio, o que prejudica o controle financeiro e o fechamento de caixa. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                       |
| -------------------------------------------------------------------------- |
| 1. Acessar a tela de contas a receber do SIFIT.                            |
| 2. Clicar em "Visualizar" de uma conta pendente.                           |
| 3. Clicar em "Efetuar Recebimento".                                        |
| 4. Não selecionar o tipo de pagamento e clicar em "Salvar".                |
| 5. Confirmar a mensagem "O caixa aberto não é de hoje, deseja continuar?". |

|                               **Comportamento Esperado**                               |                 **Comportamento Obtido**                  |
| :------------------------------------------------------------------------------------: | :-------------------------------------------------------: |
| O sistema deve exigir a seleção do tipo de pagamento antes de registrar o recebimento. | O recebimento é registrado com o tipo de pagamento vazio. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |             **Caso de Teste Relacionado**             |
| :----------------------------: | :---------------------------------------------------: |
| Contas a Receber / Recebimento | C07-CT09: Recebimento de conta sem tipo de pagamento. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:55](https://jam.dev/c/46be9dfa-3e49-40c1-a8f7-0771f9f8a67e) |

---

### 🐞 **Bug 56: Recebimento aceita valor maior que o valor a receber sem alerta**

| **ID**  | **Descrição**                                                                                                                                                                |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-056 | Ao efetuar o recebimento de uma conta de R$ 75,50 informando o valor recebido de R$ 100,00, o sistema registra o recebimento sem nenhum alerta sobre a diferença de valores. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                     |
| ---------------------------------------------------------------------------------------- |
| 1. Acessar a tela de contas a receber do SIFIT.                                          |
| 2. Clicar em "Visualizar" de uma conta pendente de R$ 75,50.                             |
| 3. Clicar em "Efetuar Recebimento".                                                      |
| 4. Informar o valor recebido de R$ 100,00, o tipo de pagamento e o local de recebimento. |
| 5. Clicar em "Salvar" e confirmar a mensagem do caixa.                                   |

|                                  **Comportamento Esperado**                                  |                  **Comportamento Obtido**                   |
| :------------------------------------------------------------------------------------------: | :---------------------------------------------------------: |
| O sistema deve alertar sobre a divergência ou impedir o recebimento acima do valor da conta. | O recebimento é registrado com R$ 100,00 sem nenhum alerta. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |                **Caso de Teste Relacionado**                 |
| :----------------------------: | :----------------------------------------------------------: |
| Contas a Receber / Recebimento | C07-CT10: Recebimento com valor maior que o valor a receber. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:56](https://jam.dev/c/f28fd023-7766-4e7e-87eb-419aad2d2797) |

---

### 🐞 **Bug 57: Ausência de mensagem quando a busca não encontra contas a receber**

| **ID**  | **Descrição**                                                                                                                                         |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-057 | Ao pesquisar um nome de cliente inexistente, o sistema exibe apenas a tabela vazia, sem nenhuma mensagem informando que nenhuma conta foi encontrada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                        |
| ----------------------------------------------------------- |
| 1. Acessar a tela de contas a receber do SIFIT.             |
| 2. Informar um nome inexistente no campo "Nome do cliente". |
| 3. Clicar no botão "Buscar".                                |
| 4. Verificar a listagem exibida.                            |

|                     **Comportamento Esperado**                      |                           **Comportamento Obtido**                           |
| :-----------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| O sistema deve exibir uma mensagem como "Nenhuma conta encontrada". | O sistema exibe somente o cabeçalho da tabela, sem registros e sem mensagem. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |         **Caso de Teste Relacionado**          |
| :------------------------: | :--------------------------------------------: |
|  Contas a Receber / Busca  | C07-CT03: Busca de conta com nome inexistente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:57](https://jam.dev/c/22ec822a-9cc2-412b-b1dd-3354f81136a8) |

---

### 🐞 **Bug 58: Busca por código inexistente exibe erro no servidor e mantém todos os fornecedores**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-058 | Ao pesquisar um código que não existe (ex.: "999"), o sistema exibe a janela "Erro no servidor - Ocorreu um erro interno no servidor" e a listagem continua exibindo todos os 8 fornecedores cadastrados, em vez de informar que nenhum fornecedor foi encontrado. Em testes anteriores, a busca por código inexistente ou parcial (ex.: "29") também retornava todos os fornecedores. A busca funciona somente com o código exato (ex.: "394"). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**        |
| ------------------------------------------- |
| 1. Acessar a tela de fornecedores do SIFIT. |
| 2. Informar "999" no campo "Código".        |
| 3. Clicar no botão "Buscar".                |
| 4. Verificar os fornecedores exibidos.      |

|                                       **Comportamento Esperado**                                        |                               **Comportamento Obtido**                                |
| :-----------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------: |
| A listagem não deve exibir fornecedores e o sistema deve informar que nenhum fornecedor foi encontrado. | O sistema exibe "Erro no servidor" e a listagem continua com todos os 8 fornecedores. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**    |             **Caso de Teste Relacionado**             |
| :-----------------------------: | :---------------------------------------------------: |
| Fornecedores / Busca por código | C08-CT04: Busca de fornecedor com código inexistente. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:58](https://jam.dev/c/7e669c65-5f1a-4cc5-b773-2062825d4618) |

---

### 🐞 **Bug 59: Erro ao cadastrar fornecedor com dados válidos**

| **ID**  | **Descrição**                                                                                                                                                                                 |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-059 | Ao salvar um novo fornecedor, o sistema exibe a mensagem "Erro ao salvar fornecedor." e o fornecedor não é cadastrado, tanto com todos os campos preenchidos quanto informando apenas o nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                   |
| ---------------------------------------------------------------------- |
| 1. Acessar a tela de fornecedores do SIFIT.                            |
| 2. Clicar no botão "Novo Fornecedor".                                  |
| 3. Informar o nome "Fornecedor Teste Ville" e os demais dados válidos. |
| 4. Clicar no botão "Salvar".                                           |
| 5. Verificar a mensagem exibida.                                       |

|                     **Comportamento Esperado**                      |                           **Comportamento Obtido**                            |
| :-----------------------------------------------------------------: | :---------------------------------------------------------------------------: |
| O sistema deve cadastrar o fornecedor e exibir mensagem de sucesso. | O sistema exibe "Erro ao salvar fornecedor." e o fornecedor não é cadastrado. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**            |
| :------------------------: | :-------------------------------------------------: |
|  Fornecedores / Cadastro   | C08-CT06: Cadastro de fornecedor com dados válidos. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:59](https://jam.dev/c/2c2c4c60-b617-44b6-8337-1cc44e327fd9) |

---

### 🐞 **Bug 60: Erro interno com exposição de SQL ao alterar fornecedor**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-060 | Ao alterar qualquer dado de um fornecedor existente (nome ou status) e clicar em "Salvar", o sistema exibe "Erro no servidor - Ocorreu um erro interno no servidor." e a alteração não é salva. No DevTools (aba Network), a resposta mostra uma mensagem do banco de dados dizendo que o tipo de pessoa (Física ou Jurídica) não pode ficar vazio. O problema ocorre com os fornecedores 299 (Jao) e 394 (Copel). Além disso, salvar com o nome vazio não é validado na tela e também gera o erro do servidor. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                 |
| ---------------------------------------------------- |
| 1. Acessar a tela de fornecedores do SIFIT.          |
| 2. Clicar no botão "Visualizar" do fornecedor "Jao". |
| 3. Clicar no ícone de edição.                        |
| 4. Alterar o nome para "Jao Teste Ville".            |
| 5. Clicar no botão "Salvar".                         |

|                        **Comportamento Esperado**                         |                           **Comportamento Obtido**                            |
| :-----------------------------------------------------------------------: | :---------------------------------------------------------------------------: |
| O sistema deve salvar a alteração e exibir o nome atualizado na listagem. | O sistema exibe "Erro no servidor" e o fornecedor permanece com o nome "Jao". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |        **Caso de Teste Relacionado**         |
| :------------------------: | :------------------------------------------: |
|  Fornecedores / Alteração  | C08-CT08: Alteração dos dados do fornecedor. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:60](https://jam.dev/c/1bd0c308-c44d-42f3-8560-57ce86b98b1b) |

---

### 🐞 **Bug 61: Check-ins realizados não aparecem na tela de Presenças**

| **ID**  | **Descrição**                                                                                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-061 | Após realizar 3 check-ins no dia (Jerome Lionel, Lila e Steven Kaiki), a tela de Presenças exibe "Total no período 0" e a mensagem "Nenhuma presença encontrada", tanto no período da semana quanto no atalho "Hoje". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Acessar a tela de check-in do SIFIT.      |
| 2. Realizar o check-in manual de um cliente. |
| 3. Acessar o menu "Presenças".               |
| 4. Clicar no atalho "Hoje".                  |

|                   **Comportamento Esperado**                    |               **Comportamento Obtido**                |
| :-------------------------------------------------------------: | :---------------------------------------------------: |
| A tela de Presenças deve listar os check-ins realizados no dia. | A tela exibe "Nenhuma presença encontrada" e total 0. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |             **Caso de Teste Relacionado**              |
| :------------------------: | :----------------------------------------------------: |
|    Check-in / Presenças    | C09-CT10: Exibição dos check-ins na tela de Presenças. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:61](coloque o link do video aqui) |

---

### 🐞 **Bug 62: Check-in permanece "Pendente" e não há retorno ao registrar entrada novamente**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-062 | Após o check-in, o cliente permanece com status "Pendente" na listagem, com o botão "Registrar entrada" disponível, e o indicador "Presentes agora" continua em 0. Ao clicar novamente em "Registrar entrada", nada acontece e nenhuma mensagem é exibida. Na janela de check-in manual, o mesmo cliente ainda aparece como "Cliente liberado para realizar o check-in.". Não existe opção para registrar a saída. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                              |
| ----------------------------------------------------------------- |
| 1. Acessar a tela de check-in do SIFIT.                           |
| 2. Realizar o check-in manual do cliente "Jerome Lionel".         |
| 3. Observar o status na listagem e o indicador "Presentes agora". |
| 4. Clicar no botão "Registrar entrada" da linha do cliente.       |

|                                                       **Comportamento Esperado**                                                        |                                         **Comportamento Obtido**                                          |
| :-------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| O cliente deve constar como presente, o indicador deve ser atualizado e uma nova tentativa deve informar que já existe check-in aberto. | O status permanece "Pendente", "Presentes agora" fica em 0 e a nova tentativa não exibe nenhuma mensagem. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |                               **Caso de Teste Relacionado**                               |
| :------------------------: | :---------------------------------------------------------------------------------------: |
|    Check-in / Listagem     | C09-CT07: Status do check-in e indicador "Presentes agora". C09-CT08: Check-in duplicado. |

|           **Evidência(s)**           |
| :----------------------------------: |
| [BUG:62](../Evidencias/C09-CT07.png) |

---

### 🐞 **Bug 63: Horário de entrada do check-in exibido com 3 horas a mais**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-063 | O check-in realizado às 18:11 (horário exibido no relógio da própria tela) é apresentado na coluna "Entrada" como 21:11, ou seja, com 3 horas de diferença, o que indica a exibição do horário em UTC em vez do horário de Brasília. Em outra execução, o check-in feito às 13:54 apareceu na coluna "Entrada" como 16:54. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                         |
| ---------------------------------------------------------------------------- |
| 1. Acessar a tela de check-in do SIFIT e observar o horário no topo da tela. |
| 2. Realizar o check-in manual de um cliente.                                 |
| 3. Observar o horário exibido na coluna "Entrada".                           |

|                        **Comportamento Esperado**                        |    **Comportamento Obtido**     |
| :----------------------------------------------------------------------: | :-----------------------------: |
| A coluna "Entrada" deve exibir o horário local do check-in (ex.: 18:11). | A coluna "Entrada" exibe 21:11. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |               **Caso de Teste Relacionado**               |
| :------------------------: | :-------------------------------------------------------: |
|    Check-in / Listagem     | C09-CT03: Check-in manual de cliente com matrícula ativa. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:63](https://jam.dev/c/26554c0c-5651-4795-968e-f46eb3ccf1ea) |

---

### 🐞 **Bug 64: Cliente sem matrícula ativa é liberado para check-in**

| **ID**  | **Descrição**                                                                                                                                                                                                                       |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-064 | Ao selecionar no check-in manual a cliente "Lila", que não possui matrícula ativa (consta como "Sem Matrícula" na tela de Clientes), o sistema exibe "Cliente liberado para realizar o check-in." e registra a entrada normalmente. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                              |
| ----------------------------------------------------------------- |
| 1. Acessar a tela de check-in do SIFIT.                           |
| 2. Clicar em "Check-in manual".                                   |
| 3. Pesquisar e selecionar a cliente "Lila" (sem matrícula ativa). |
| 4. Clicar em "Registrar entrada".                                 |

|                               **Comportamento Esperado**                                |        **Comportamento Obtido**         |
| :-------------------------------------------------------------------------------------: | :-------------------------------------: |
| O sistema deve informar que a cliente não possui matrícula ativa e bloquear o check-in. | O sistema libera e registra o check-in. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  |           **Caso de Teste Relacionado**            |
| :-------------------------: | :------------------------------------------------: |
| Check-in / Regras de acesso | C09-CT04: Check-in de cliente sem matrícula ativa. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:64](coloque o link do video aqui) |

---

### 🐞 **Bug 65: Ausência de mensagens no check-in manual e na entrada rápida**

| **ID**  | **Descrição**                                                                                                                                                                                                                          |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-065 | Ao registrar um check-in com sucesso (manual ou pela entrada rápida), nenhuma mensagem de confirmação é exibida. Ao clicar em "Realizar check-in" com o campo "Código do cliente" vazio, nada acontece e nenhuma orientação é exibida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                 |
| ------------------------------------------------------------------------------------ |
| 1. Acessar a tela de check-in do SIFIT.                                              |
| 2. Manter o campo "Código do cliente" vazio e clicar em "Realizar check-in".         |
| 3. Informar o código de um cliente ativo (ex.: 406) e clicar em "Realizar check-in". |
| 4. Observar as mensagens exibidas.                                                   |

|                                    **Comportamento Esperado**                                    |          **Comportamento Obtido**          |
| :----------------------------------------------------------------------------------------------: | :----------------------------------------: |
| O sistema deve solicitar o código quando o campo estiver vazio e confirmar o check-in realizado. | Nenhuma mensagem é exibida nos dois casos. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

|     **Funcionalidade Afetada**     |                                 **Caso de Teste Relacionado**                                  |
| :--------------------------------: | :--------------------------------------------------------------------------------------------: |
| Check-in / Entrada rápida e manual | C09-CT06: Entrada rápida sem código. C09-CT03: Check-in manual de cliente com matrícula ativa. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:65](https://jam.dev/c/569cdd92-c448-4afe-bcc1-cd034d787e0a) |

---

### 🐞 **Bug 66: Erro ao salvar avaliação realizada**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                      |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-066 | Ao clicar em "Fazer Avaliação", informar altura (1,75) e peso (80) e clicar em "Salvar", o sistema exibe "Erro ao salvar avaliação" e a avaliação permanece "PENDENTE". O mesmo ocorre ao salvar sem medidas, caso em que o sistema também não orienta o preenchimento dos campos. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                    |
| ------------------------------------------------------- |
| 1. Acessar a tela de avaliações do SIFIT.               |
| 2. Cadastrar uma avaliação para o aluno "Steven Kaiki". |
| 3. Clicar em "Fazer Avaliação" na linha da avaliação.   |
| 4. Informar altura "1,75" e peso "80".                  |
| 5. Clicar no botão "Salvar".                            |

|                       **Comportamento Esperado**                       |                           **Comportamento Obtido**                           |
| :--------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| O sistema deve salvar a avaliação e alterar o status para "REALIZADO". | O sistema exibe "Erro ao salvar avaliação" e a avaliação permanece pendente. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**  |       **Caso de Teste Relacionado**        |
| :--------------------------: | :----------------------------------------: |
| Avaliações / Fazer avaliação | C10-CT10: Registro da avaliação realizada. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:66](coloque o link do video aqui) |

---

### 🐞 **Bug 67: Alteração de data e hora da avaliação não é salva**

| **ID**  | **Descrição**                                                                                                                                                                                                                                           |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-067 | Na janela "Alterar Data / Hora", ao informar a nova data (26/10/2026) e a nova hora (11:00) e clicar em "Salvar", nada acontece, nenhuma mensagem é exibida e a avaliação permanece com a data e a hora originais. O mesmo ocorre com os campos vazios. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                        |
| ----------------------------------------------------------- |
| 1. Acessar a tela de avaliações do SIFIT.                   |
| 2. Clicar no botão "Alterar" de uma avaliação pendente.     |
| 3. Informar a nova data "26/10/2026" e a nova hora "11:00". |
| 4. Clicar no botão "Salvar".                                |
| 5. Verificar a data e a hora na listagem.                   |

|                    **Comportamento Esperado**                     |                   **Comportamento Obtido**                    |
| :---------------------------------------------------------------: | :-----------------------------------------------------------: |
| O sistema deve salvar a nova data e hora e confirmar a alteração. | Nada acontece e a avaliação mantém a data e a hora originais. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|      **Funcionalidade Afetada**       |          **Caso de Teste Relacionado**           |
| :-----------------------------------: | :----------------------------------------------: |
| Avaliações / Alteração de data e hora | C10-CT08: Alteração da data e hora da avaliação. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:67](coloque o link do video aqui) |

---

### 🐞 **Bug 68: Cadastro de avaliação aceita hora inválida e retorna erro interno**

| **ID**  | **Descrição**                                                                                                                                                                       |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-068 | O campo de hora aceita valores inexistentes, como "25:99". Ao salvar, o sistema exibe a mensagem genérica "Erro ao cadastrar Avaliação.", em vez de informar que a hora é inválida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                   |
| ------------------------------------------------------ |
| 1. Acessar a tela de avaliações do SIFIT.              |
| 2. Clicar em "Cadastrar Avaliação".                    |
| 3. Selecionar o aluno "Lila" e o personal "Gabriella". |
| 4. Informar a hora "25:99".                            |
| 5. Clicar no botão "Salvar".                           |

|                        **Comportamento Esperado**                         |            **Comportamento Obtido**             |
| :-----------------------------------------------------------------------: | :---------------------------------------------: |
| O sistema deve informar que a hora é inválida antes de enviar o cadastro. | O sistema exibe "Erro ao cadastrar Avaliação.". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**            |
| :------------------------: | :------------------------------------------------: |
|   Avaliações / Cadastro    | C10-CT06: Cadastro de avaliação com hora inválida. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:68](coloque o link do video aqui) |

---

### 🐞 **Bug 69: IMC exibido sem formatação**

| **ID**  | **Descrição**                                                                                                                                                 |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-069 | Ao informar altura 1,75 e peso 80 na tela "Fazer Avaliação", o campo "IMC" exibe "26.122448979591837", com ponto como separador decimal e sem arredondamento. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                      |
| --------------------------------------------------------- |
| 1. Acessar a tela de avaliações do SIFIT.                 |
| 2. Clicar em "Fazer Avaliação" de uma avaliação pendente. |
| 3. Informar altura "1,75" e peso "80".                    |
| 4. Observar o campo "IMC".                                |

|      **Comportamento Esperado**      |          **Comportamento Obtido**          |
| :----------------------------------: | :----------------------------------------: |
| O IMC deve ser exibido como "26,12". | O IMC é exibido como "26.122448979591837". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**  | **Caso de Teste Relacionado** |
| :--------------------------: | :---------------------------: |
| Avaliações / Fazer avaliação |   C10-CT09: Cálculo do IMC.   |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:69](coloque o link do video aqui) |

---

### 🐞 **Bug 70: Erro ao salvar alterações da turma**

| **ID**  | **Descrição**                                                                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-070 | Ao clicar em "Editar" de qualquer turma e em "Salvar", o sistema exibe "Erro ao salvar turma.". O erro ocorre ao alterar nome, horário ou status e até ao salvar sem nenhuma alteração (testado nas turmas #10 e #11). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                   |
| ------------------------------------------------------ |
| 1. Acessar a tela de turmas do SIFIT.                  |
| 2. Clicar no botão "Editar" da turma "Turma do Ville". |
| 3. Clicar no botão "Salvar" sem alterar nenhum campo.  |
| 4. Verificar a mensagem exibida.                       |

|                 **Comportamento Esperado**                  |                       **Comportamento Obtido**                       |
| :---------------------------------------------------------: | :------------------------------------------------------------------: |
| O sistema deve salvar a turma e exibir mensagem de sucesso. | O sistema exibe "Erro ao salvar turma." e nenhuma alteração é salva. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
|     Turmas / Alteração     | C11-CT10: Alteração de turma. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:70](https://jam.dev/c/e0e2ffd3-1142-433c-b5b9-fbdc31a6ac9c) |

---

### 🐞 **Bug 71: Cadastro de turma aceita hora final anterior à hora inicial**

| **ID**  | **Descrição**                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-071 | O sistema permite cadastrar uma turma com hora inicial 11:00 e hora final 10:00. A turma é salva e exibida na listagem com o horário "11:00:00 - 10:00:00". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                |
| ----------------------------------------------------------------------------------- |
| 1. Acessar a tela de turmas do SIFIT.                                               |
| 2. Clicar em "Cadastrar Turma".                                                     |
| 3. Informar o nome "Turma Teste Ville Horario", o plano "Treino Livre" e o dia Seg. |
| 4. Informar a hora inicial 11:00 e a hora final 10:00.                              |
| 5. Clicar no botão "Salvar".                                                        |

|                         **Comportamento Esperado**                          |                 **Comportamento Obtido**                  |
| :-------------------------------------------------------------------------: | :-------------------------------------------------------: |
| O sistema deve informar que a hora final deve ser maior que a hora inicial. | A turma é cadastrada com o horário "11:00:00 - 10:00:00". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |                 **Caso de Teste Relacionado**                  |
| :------------------------: | :------------------------------------------------------------: |
|     Turmas / Cadastro      | C11-CT09: Cadastro de turma com hora final anterior à inicial. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:71](https://jam.dev/c/27a62498-c64a-4479-a706-29a846758f0c) |

---

### 🐞 **Bug 72: Fechamento de caixa não é salvo após "Buscar Contas"**

| **ID**  | **Descrição**                                                                                                                                                                                                                                            |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-072 | Na janela "Fechamento de Caixa", após selecionar o local e clicar em "Buscar Contas", o botão "Salvar" não executa nenhuma ação: nada acontece e o caixa permanece "ABERTO". O fechamento só é salvo quando o usuário não busca as contas (ver BUG-073). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                         |
| ------------------------------------------------------------ |
| 1. Acessar a tela de caixas do SIFIT.                        |
| 2. Clicar em "Visualizar" de um caixa aberto.                |
| 3. Selecionar o local de contas e clicar em "Buscar Contas". |
| 4. Clicar no botão "Salvar".                                 |
| 5. Verificar o status do caixa na listagem.                  |

|             **Comportamento Esperado**             |         **Comportamento Obtido**          |
| :------------------------------------------------: | :---------------------------------------: |
| O caixa deve ser fechado com os totais conferidos. | Nada acontece e o caixa permanece aberto. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |               **Caso de Teste Relacionado**               |
| :------------------------: | :-------------------------------------------------------: |
|    Caixas / Fechamento     | C12-CT10: Fechamento de caixa com conferência das contas. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:72](https://jam.dev/c/aa6da264-81a2-49bb-8666-d1fd604e8d8a) |

---

### 🐞 **Bug 73: Caixa pode ser fechado sem a conferência das contas**

| **ID**  | **Descrição**                                                                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-073 | Embora a janela oriente "Confira o periodo, busque as contas e valide os totais antes de salvar", ao clicar em "Salvar" sem buscar as contas o caixa é fechado com todos os totais zerados (entradas, saídas e total). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                       |
| ---------------------------------------------------------- |
| 1. Acessar a tela de caixas do SIFIT.                      |
| 2. Clicar em "Visualizar" de um caixa aberto.              |
| 3. Clicar no botão "Salvar" sem clicar em "Buscar Contas". |
| 4. Verificar o status do caixa na listagem.                |

|                          **Comportamento Esperado**                           |         **Comportamento Obtido**         |
| :---------------------------------------------------------------------------: | :--------------------------------------: |
| O sistema deve exigir a busca e a conferência das contas antes do fechamento. | O caixa é fechado com os totais zerados. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**            |
| :------------------------: | :-------------------------------------------------: |
|    Caixas / Fechamento     | C12-CT11: Fechamento de caixa sem buscar as contas. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:73](https://jam.dev/c/765bd31b-51f2-4c38-901c-69fd16c38677) |

---

### 🐞 **Bug 74: Sistema permite abrir mais de um caixa no mesmo local**

| **ID**  | **Descrição**                                                                                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-074 | Com um caixa já aberto no local "Teste2", foi possível abrir um segundo caixa no mesmo local e na mesma data (caixas #29 e #30). O sistema passou a ter 5 caixas abertos para apenas 4 locais. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                |
| ------------------------------------------------------------------- |
| 1. Acessar a tela de caixas do SIFIT.                               |
| 2. Abrir um caixa no local "Teste2".                                |
| 3. Clicar novamente em "Abrir Caixa" e selecionar o local "Teste2". |
| 4. Clicar no botão "Salvar".                                        |

|                     **Comportamento Esperado**                      |         **Comportamento Obtido**          |
| :-----------------------------------------------------------------: | :---------------------------------------: |
| O sistema deve informar que já existe um caixa aberto para o local. | Um segundo caixa é aberto no mesmo local. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |             **Caso de Teste Relacionado**             |
| :------------------------: | :---------------------------------------------------: |
|     Caixas / Abertura      | C12-CT08: Abertura de caixa duplicado no mesmo local. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:74](https://jam.dev/c/72e7c612-fc70-4d19-a5e1-5343c9fa0225) |

---

### 🐞 **Bug 75: Listagem inicial de caixas ignora o período exibido no filtro**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-075 | Ao acessar a tela, o filtro exibe o período de 01/10/2026 a 31/10/2026, mas a listagem mostra todos os 20 caixas (de 2022 a 2026) e o indicador "Registros no Periodo" exibe 20. Somente após clicar em "Buscar" o período é aplicado e a listagem passa a exibir 1 caixa. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                                      |
| ------------------------------------------------------------------------- |
| 1. Acessar a tela de caixas do SIFIT.                                     |
| 2. Observar o período exibido nos filtros e as datas dos caixas listados. |
| 3. Clicar no botão "Buscar" sem alterar os filtros.                       |
| 4. Comparar a quantidade de caixas exibidos.                              |

|                            **Comportamento Esperado**                            |                  **Comportamento Obtido**                  |
| :------------------------------------------------------------------------------: | :--------------------------------------------------------: |
| A listagem inicial deve exibir somente os caixas do período exibido nos filtros. | A listagem inicial exibe todos os caixas, fora do período. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |             **Caso de Teste Relacionado**              |
| :------------------------: | :----------------------------------------------------: |
|     Caixas / Listagem      | C12-CT02: Listagem inicial conforme o período exibido. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:75](https://jam.dev/c/82036612-21df-45fd-9051-b8b1a767a3c2) |

---

### 🐞 **Bug 76: Não é possível registrar o pagamento de conta a pagar**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-076 | Não existe opção para registrar o pagamento de uma conta pendente: a linha da listagem possui apenas os botões "Visualizar" e "Deletar", e a janela "Visualizar Conta a Pagar" possui apenas o botão "Fechar". Assim, as contas permanecem "PENDENTE" indefinidamente. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                              |
| ----------------------------------------------------------------- |
| 1. Acessar a tela de contas a pagar do SIFIT.                     |
| 2. Cadastrar uma conta pendente para o fornecedor "Centrion Web". |
| 3. Procurar na linha da conta uma opção de pagamento.             |
| 4. Clicar em "Visualizar" e procurar uma opção de pagamento.      |

|                          **Comportamento Esperado**                           |             **Comportamento Obtido**             |
| :---------------------------------------------------------------------------: | :----------------------------------------------: |
| O sistema deve permitir registrar o pagamento e alterar o status para "PAGO". | Não há nenhuma opção para registrar o pagamento. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |       **Caso de Teste Relacionado**       |
| :------------------------: | :---------------------------------------: |
| Contas a Pagar / Pagamento | C13-CT08: Registro do pagamento da conta. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:76](coloque o link do video aqui) |

---

### 🐞 **Bug 77: Indicadores "Total a Pagar" e "Valor Restante" exibem zero**

| **ID**  | **Descrição**                                                                                                                                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-077 | Com contas pendentes listadas (ex.: R$ 200,00 da conta 24 e R$ 50,00 da conta de teste), os indicadores "Total a Pagar" e "Valor Restante" permanecem em 0, enquanto "Contas Listadas" é atualizado corretamente. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                           |
| -------------------------------------------------------------- |
| 1. Acessar a tela de contas a pagar do SIFIT.                  |
| 2. Observar as contas pendentes listadas no período.           |
| 3. Observar os indicadores "Total a Pagar" e "Valor Restante". |

|                      **Comportamento Esperado**                      | **Comportamento Obtido** |
| :------------------------------------------------------------------: | :----------------------: |
| Os indicadores devem exibir a soma dos valores das contas pendentes. | Os indicadores exibem 0. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**  |       **Caso de Teste Relacionado**       |
| :--------------------------: | :---------------------------------------: |
| Contas a Pagar / Indicadores | C13-CT04: Indicadores de valores a pagar. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:77](coloque o link do video aqui) |

---

### 🐞 **Bug 78: Erro no servidor exibido após excluir conta a pagar**

| **ID**  | **Descrição**                                                                                                                                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-078 | Ao confirmar a exclusão de uma conta a pagar, a conta é excluída, mas em seguida o sistema exibe "Erro no servidor - Erro interno inesperado.", pois tenta carregar novamente a conta que acabou de ser removida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                  |
| ----------------------------------------------------- |
| 1. Acessar a tela de contas a pagar do SIFIT.         |
| 2. Clicar em "Deletar" de uma conta de teste.         |
| 3. Confirmar a mensagem "Deseja deletar esta conta?". |
| 4. Verificar a mensagem exibida.                      |

|                  **Comportamento Esperado**                  |                  **Comportamento Obtido**                   |
| :----------------------------------------------------------: | :---------------------------------------------------------: |
| O sistema deve excluir a conta e exibir mensagem de sucesso. | A conta é excluída, mas o sistema exibe "Erro no servidor". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |    **Caso de Teste Relacionado**     |
| :------------------------: | :----------------------------------: |
| Contas a Pagar / Exclusão  | C13-CT09: Exclusão de conta a pagar. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:78](coloque o link do video aqui) |

---

### 🐞 **Bug 79: Visualização da conta a pagar exibe códigos internos e campos vazios**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                           |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-079 | Na janela "Visualizar Conta a Pagar", o campo "Codigo" fica vazio, o tipo é exibido como "DESPESA_FORNECEDOR", a categoria e o tipo de documento são exibidos pelo código interno (ex.: "Categoria 3", "Tipo 1") e a data de emissão é exibida no formato "2026-10-25". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**          |
| --------------------------------------------- |
| 1. Acessar a tela de contas a pagar do SIFIT. |
| 2. Clicar em "Visualizar" de uma conta.       |
| 3. Observar os campos exibidos.               |

|                                           **Comportamento Esperado**                                           |                              **Comportamento Obtido**                              |
| :------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------: |
| A visualização deve exibir o código da conta, a categoria e o tipo pelo nome e as datas no formato dd/mm/aaaa. | São exibidos códigos internos, campo de código vazio e data no formato aaaa-mm-dd. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**   |      **Caso de Teste Relacionado**       |
| :---------------------------: | :--------------------------------------: |
| Contas a Pagar / Visualização | C13-CT07: Visualização da conta a pagar. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:79](coloque o link do video aqui) |

---

### 🐞 **Bug 80: Despesa fixa aceita valor negativo e erro interno com valor em texto**

| **ID**  | **Descrição**                                                                                                                                                                                                  |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-080 | O campo "Valor" da despesa fixa não possui validação: o valor "-100" é aceito e a despesa é cadastrada com "-R$ 100,00"; ao informar "abc", o sistema exibe a mensagem genérica "Erro ao salvar despesa fixa". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                |
| ------------------------------------------------------------------- |
| 1. Acessar a tela de despesas fixas do SIFIT.                       |
| 2. Clicar em "Nova Despesa".                                        |
| 3. Informar o nome "Despesa Teste Ville Negativa" e o valor "-100". |
| 4. Clicar no botão "Salvar Despesa".                                |
| 5. Verificar a despesa na listagem.                                 |

|                     **Comportamento Esperado**                     |          **Comportamento Obtido**          |
| :----------------------------------------------------------------: | :----------------------------------------: |
| O sistema deve aceitar somente valores numéricos maiores que zero. | A despesa é cadastrada com valor negativo. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |             **Caso de Teste Relacionado**              |
| :------------------------: | :----------------------------------------------------: |
| Despesas Fixas / Cadastro  | C13-CT13: Cadastro de despesa fixa com valor negativo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:80](coloque o link do video aqui) |

---

### 🐞 **Bug 81: Ficha de treino não pode ser aberta nem salva**

| **ID**  | **Descrição**                                                                                                                                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-081 | Após criar a ficha, a tela de montagem dos treinos é exibida, mas ao clicar em "Salvar Ficha" o sistema exibe "Erro no servidor - Erro interno inesperado.". Ao clicar em "Visualizar" na listagem, o sistema também exibe "Erro no servidor". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                           |
| ------------------------------------------------------------------------------ |
| 1. Cadastrar um objetivo em "Objetivos Treino" (pré-requisito).                |
| 2. Acessar "Ficha de Treino" e clicar em "Cadastrar Ficha".                    |
| 3. Selecionar o aluno, o personal e o objetivo e clicar em "Criar Nova Ficha". |
| 4. Clicar em "Adicionar Treino" e depois em "Salvar Ficha".                    |
| 5. Voltar à listagem e clicar em "Visualizar" da ficha.                        |

|                      **Comportamento Esperado**                       |                       **Comportamento Obtido**                        |
| :-------------------------------------------------------------------: | :-------------------------------------------------------------------: |
| O sistema deve salvar os treinos e permitir abrir a ficha cadastrada. | O sistema exibe "Erro no servidor" ao salvar e ao visualizar a ficha. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|         **Funcionalidade Afetada**         |                                  **Caso de Teste Relacionado**                                   |
| :----------------------------------------: | :----------------------------------------------------------------------------------------------: |
| Fichas de Treino / Montagem e visualização | C14-CT05: Montagem e salvamento dos treinos da ficha. C14-CT06: Visualização da ficha de treino. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:81](coloque o link do video aqui) |

---

### 🐞 **Bug 82: Mensagem genérica ao criar ficha sem objetivo do treino**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-082 | Ao criar a ficha sem objetivo, o sistema exibe apenas "Erro ao salvar Ficha.". A tela não diz que o objetivo é obrigatório. Além disso, o campo "Objetivo" não apresenta opções quando não há objetivos cadastrados, sem orientar o usuário a cadastrá-los em "Objetivos Treino". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                          |
| ------------------------------------------------------------- |
| 1. Acessar "Ficha de Treino" e clicar em "Cadastrar Ficha".   |
| 2. Selecionar o aluno "Steven Kaiki" e o personal "Santhago". |
| 3. Não selecionar o objetivo (campo sem opções).              |
| 4. Clicar em "Criar Nova Ficha".                              |

|                                 **Comportamento Esperado**                                  |         **Comportamento Obtido**         |
| :-----------------------------------------------------------------------------------------: | :--------------------------------------: |
| O sistema deve informar "Escolha o objetivo do treino." e orientar o cadastro de objetivos. | O sistema exibe "Erro ao salvar Ficha.". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  |       **Caso de Teste Relacionado**       |
| :-------------------------: | :---------------------------------------: |
| Fichas de Treino / Cadastro | C14-CT03: Cadastro de ficha sem objetivo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:82](coloque o link do video aqui) |

---

### 🐞 **Bug 83: Exclusão de ficha de treino expõe comandos SQL**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                   |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-083 | Ao excluir uma ficha de treino, a exclusão é realizada, porém no DevTools (aba Network), a resposta mostra o comando SQL executado e os parâmetros ("DELETE FROM ficha_treino WHERE id = 1 AND empresa_id = ..."), expondo detalhes internos do banco de dados. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                      |
| --------------------------------------------------------- |
| 1. Acessar "Ficha de Treino".                             |
| 2. Abrir o DevTools do navegador na aba "Network".        |
| 3. Clicar em "Deletar" de uma ficha de teste e confirmar. |
| 4. Na aba Network, abrir a resposta da exclusão.          |

|                           **Comportamento Esperado**                           |                **Comportamento Obtido**                 |
| :----------------------------------------------------------------------------: | :-----------------------------------------------------: |
| A resposta deve trazer apenas o resultado da operação, sem expor comandos SQL. | No DevTools, a resposta mostra o comando SQL executado. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada**  |     **Caso de Teste Relacionado**      |
| :-------------------------: | :------------------------------------: |
| Fichas de Treino / Exclusão | C14-CT07: Exclusão de ficha de treino. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:83](coloque o link do video aqui) |

---

### 🐞 **Bug 84: Sistema permite cadastrar exercício duplicado no mesmo grupo**

| **ID**  | **Descrição**                                                                                                                                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-084 | É possível cadastrar duas vezes o mesmo exercício no mesmo grupo muscular, sem nenhum aviso. Em uma das execuções, um exercício de teste foi cadastrado duas vezes no grupo "Peitoral" e o total passou de 6 para 7. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                                              |
| --------------------------------------------------------------------------------- |
| 1. Acessar a tela de exercícios do SIFIT.                                         |
| 2. Clicar em "Adicionar" no grupo "Peitoral" e cadastrar "Exercício Teste Ville". |
| 3. Repetir o cadastro com o mesmo nome no mesmo grupo.                            |
| 4. Verificar o grupo "Peitoral".                                                  |

|                      **Comportamento Esperado**                      |         **Comportamento Obtido**         |
| :------------------------------------------------------------------: | :--------------------------------------: |
| O sistema deve informar que o exercício já está cadastrado no grupo. | O exercício é cadastrado em duplicidade. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |       **Caso de Teste Relacionado**        |
| :------------------------: | :----------------------------------------: |
|   Exercícios / Cadastro    | C14-CT11: Cadastro de exercício duplicado. |

|                         **Evidência(s)**                         |
| :--------------------------------------------------------------: |
| [BUG:84](https://jam.dev/c/a84d54b0-8ca9-4871-9a16-5c563024a8f4) |

---

### 🐞 **Bug 85: Sistema permite cadastrar lead duplicado**

| **ID**  | **Descrição**                                                                                                                                                                                                                 |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-085 | Foi possível cadastrar duas vezes o lead "Lead Teste Ville" com o mesmo e-mail (lead.ville@teste.com) e o mesmo telefone ((44) 99999-0000), sem nenhum aviso. Os dois registros passam a constar na listagem (códigos 6 e 7). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                |
| ----------------------------------------------------------------------------------- |
| 1. Acessar a tela de prospecção do SIFIT.                                           |
| 2. Cadastrar o lead "Lead Teste Ville" com e-mail e telefone.                       |
| 3. Clicar novamente em "Adicionar Lead" e informar o mesmo nome, e-mail e telefone. |
| 4. Clicar no botão "Salvar Lead".                                                   |
| 5. Verificar a listagem.                                                            |

|                          **Comportamento Esperado**                           |      **Comportamento Obtido**       |
| :---------------------------------------------------------------------------: | :---------------------------------: |
| O sistema deve informar que já existe um lead com o mesmo e-mail ou telefone. | O lead é cadastrado em duplicidade. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**   |     **Caso de Teste Relacionado**     |
| :---------------------------: | :-----------------------------------: |
| Prospecção / Cadastro de lead | C15-CT10: Cadastro de lead duplicado. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:85](coloque o link do video aqui) |

---

### 🐞 **Bug 86: Busca de colaborador por código inexistente exibe linha vazia**

| **ID**  | **Descrição**                                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-086 | Ao pesquisar o código "999" na tela de colaboradores, a listagem exibe uma linha vazia contendo apenas "/", em vez de informar que nenhum colaborador foi encontrado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Acessar a tela de colaboradores do SIFIT. |
| 2. Informar "999" no campo "Código".         |
| 3. Clicar no botão "Buscar".                 |
| 4. Verificar a listagem exibida.             |

|                   **Comportamento Esperado**                   |         **Comportamento Obtido**          |
| :------------------------------------------------------------: | :---------------------------------------: |
| O sistema deve informar que nenhum colaborador foi encontrado. | A listagem exibe uma linha vazia com "/". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |             **Caso de Teste Relacionado**              |
| :------------------------: | :----------------------------------------------------: |
|   Colaboradores / Busca    | C16-CT03: Busca de colaborador com código inexistente. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:86](https://jam.dev/c/fd885338-b1b1-4689-8a94-a0de9885af05) |

---

### 🐞 **Bug 87: Alteração de colaborador expõe comandos SQL**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-087 | Ao salvar a alteração de um colaborador, a alteração é realizada, porém no DevTools (aba Network), a resposta mostra o comando SQL executado ("UPDATE pessoas SET nome = :nome, cpf = :cpf, ...") e seus parâmetros, expondo detalhes internos do banco de dados. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                        |
| ----------------------------------------------------------- |
| 1. Acessar o perfil de um colaborador e clicar em "Editar". |
| 2. Abrir o DevTools do navegador na aba "Network".          |
| 3. Alterar o nome e clicar em "Salvar".                     |
| 4. Na aba Network, abrir a resposta da alteração.           |

|                           **Comportamento Esperado**                           |                **Comportamento Obtido**                 |
| :----------------------------------------------------------------------------: | :-----------------------------------------------------: |
| A resposta deve trazer apenas o resultado da operação, sem expor comandos SQL. | No DevTools, a resposta mostra o comando SQL executado. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |    **Caso de Teste Relacionado**    |
| :------------------------: | :---------------------------------: |
| Colaboradores / Alteração  | C16-CT07: Alteração de colaborador. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:87](https://jam.dev/c/4c015a99-0c38-4e9d-a68b-3e38d60df197) |
| [Print](../Evidencias/C16-CT07.png) |

---

### 🐞 **Bug 88: Funções não podem ser alteradas nem excluídas**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-088 | Na tela de funções, a janela aberta pelo botão "Visualizar" exibe todos os campos somente para leitura, com os botões "Fechar" e "Voltar", e a listagem não possui botão de exclusão. Assim, uma função cadastrada com erro (ex.: duplicada) não pode ser corrigida nem removida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                     |
| -------------------------------------------------------- |
| 1. Acessar a tela de funções do SIFIT.                   |
| 2. Clicar em "Visualizar" de uma função.                 |
| 3. Tentar alterar o nome da função.                      |
| 4. Procurar na listagem uma opção para excluir a função. |

|             **Comportamento Esperado**             |                 **Comportamento Obtido**                  |
| :------------------------------------------------: | :-------------------------------------------------------: |
| O sistema deve permitir alterar e excluir funções. | Os campos são somente leitura e não há opção de exclusão. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|   **Funcionalidade Afetada**   |       **Caso de Teste Relacionado**       |
| :----------------------------: | :---------------------------------------: |
| Funções / Alteração e exclusão | C16-CT16: Alteração e exclusão de função. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:88](https://jam.dev/c/cf5d18c4-dc37-4ca9-af67-469cb7f230d2) |

---

### 🐞 **Bug 89: Sistema permite cadastrar função duplicada**

| **ID**  | **Descrição**                                                                                                                                                                               |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-089 | Foi possível cadastrar duas vezes a função "Função Teste Ville" (códigos #9 e #10), sem nenhum aviso. Como funções não podem ser excluídas (BUG-088), a duplicidade não pode ser corrigida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                          |
| ------------------------------------------------------------- |
| 1. Acessar a tela de funções do SIFIT.                        |
| 2. Cadastrar a função "Função Teste Ville".                   |
| 3. Clicar novamente em "Nova Função" e informar o mesmo nome. |
| 4. Clicar no botão "Salvar Função".                           |

|           **Comportamento Esperado**            |       **Comportamento Obtido**        |
| :---------------------------------------------: | :-----------------------------------: |
| O sistema deve informar que a função já existe. | A função é cadastrada em duplicidade. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |      **Caso de Teste Relacionado**      |
| :------------------------: | :-------------------------------------: |
|     Funções / Cadastro     | C16-CT15: Cadastro de função duplicada. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:89](https://jam.dev/c/05a2cb17-c81f-45f1-a9be-05fa709d4f82) |

---

### 🐞 **Bug 90: Produto do tipo Pontuação não pode ser cadastrado**

| **ID**  | **Descrição**                                                                                                                                                                                                                        |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-090 | Ao selecionar o tipo "Pontuação", o campo "Preço" é substituído pelo campo "Pontuação". Ao salvar o produto com 100 pontos, o sistema exibe "Erro ao salvar produto". Assim, nenhum produto de troca por pontos pode ser cadastrado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                  |
| --------------------------------------------------------------------- |
| 1. Acessar a tela de produtos do SIFIT e clicar em "Novo".            |
| 2. Informar o nome "Produto Teste Ville Pontos".                      |
| 3. Selecionar o tipo "Pontuação" e informar 100 no campo "Pontuação". |
| 4. Clicar no botão "Salvar".                                          |

|                      **Comportamento Esperado**                      |                        **Comportamento Obtido**                        |
| :------------------------------------------------------------------: | :--------------------------------------------------------------------: |
| O sistema deve cadastrar o produto do tipo Pontuação com 100 pontos. | O sistema exibe "Erro ao salvar produto" e o produto não é cadastrado. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |          **Caso de Teste Relacionado**           |
| :------------------------: | :----------------------------------------------: |
|    Produtos / Cadastro     | C17-CT07: Cadastro de produto do tipo Pontuação. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:90](coloque o link do video aqui) |

---

### 🐞 **Bug 91: Sistema permite cadastrar produto com preço negativo**

| **ID**  | **Descrição**                                                                                                                                            |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-091 | O campo "Preço" aceita valores negativos: o produto "Produto Teste Ville Negativo" foi cadastrado com o preço "-50" e exibido na listagem como "R$ -50". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                               |
| ------------------------------------------------------------------ |
| 1. Acessar a tela de produtos do SIFIT e clicar em "Novo".         |
| 2. Informar o nome "Produto Teste Ville Negativo" e o preço "-50". |
| 3. Clicar no botão "Salvar".                                       |
| 4. Verificar o produto na listagem.                                |

|                  **Comportamento Esperado**                  |          **Comportamento Obtido**          |
| :----------------------------------------------------------: | :----------------------------------------: |
| O sistema deve informar que o preço deve ser maior que zero. | O produto é cadastrado com preço negativo. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |           **Caso de Teste Relacionado**           |
| :------------------------: | :-----------------------------------------------: |
|    Produtos / Cadastro     | C17-CT05: Cadastro de produto com preço negativo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:91](coloque o link do video aqui) |

---

### 🐞 **Bug 92: Valores dos produtos exibidos sem formatação monetária**

| **ID**  | **Descrição**                                                                                                                                                                           |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-092 | Na listagem de produtos, os valores são exibidos sem separador de milhar, sem casas decimais fixas e com ponto como separador decimal, por exemplo "R$ 1550", "R$ 7000.99" e "R$ 49.9". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**    |
| --------------------------------------- |
| 1. Acessar a tela de produtos do SIFIT. |
| 2. Observar a coluna "Valor / Pontos".  |

|                          **Comportamento Esperado**                           |                     **Comportamento Obtido**                      |
| :---------------------------------------------------------------------------: | :---------------------------------------------------------------: |
| Os valores devem ser exibidos como "R$ 1.550,00", "R$ 7.000,99" e "R$ 49,90". | Os valores são exibidos como "R$ 1550", "R$ 7000.99" e "R$ 49.9". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

| **Funcionalidade Afetada** |       **Caso de Teste Relacionado**       |
| :------------------------: | :---------------------------------------: |
|    Produtos / Listagem     | C17-CT08: Exibição do valor dos produtos. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:92](coloque o link do video aqui) |

---

### 🐞 **Bug 93: Anamneses aplicadas não aparecem na listagem**

| **ID**  | **Descrição**                                                                                                                                                                           |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-093 | Após finalizar a anamnese do aluno Steven Kaiki (o assistente termina sem erro), a tela de fichas de anamnese continua exibindo "Nenhuma ficha encontrada" e todos os indicadores em 0. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                       |
| ---------------------------------------------------------- |
| 1. Acessar "Fichas Anamnese" e clicar em "Nova Anamnese".  |
| 2. Selecionar o aluno "Steven Kaiki" e o modelo "Triplet". |
| 3. Clicar em "Iniciar" e em "Finalizar Anamnese".          |
| 4. Verificar a listagem e os indicadores.                  |

|                         **Comportamento Esperado**                          |                           **Comportamento Obtido**                            |
| :-------------------------------------------------------------------------: | :---------------------------------------------------------------------------: |
| A anamnese deve constar na listagem e os indicadores devem ser atualizados. | A listagem exibe "Nenhuma ficha encontrada" e os indicadores permanecem em 0. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|  **Funcionalidade Afetada**   |        **Caso de Teste Relacionado**        |
| :---------------------------: | :-----------------------------------------: |
| Fichas de Anamnese / Listagem | C18-CT07: Listagem das anamneses aplicadas. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:93](coloque o link do video aqui) |

---

### 🐞 **Bug 94: Perguntas do modelo de anamnese não são exibidas**

| **ID**  | **Descrição**                                                                                                                                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-094 | O modelo "Triplet" informa "1 perguntas", mas ao clicar em "Iniciar" o assistente vai direto para a etapa "Revisar e Finalizar", sem exibir a pergunta. A anamnese é finalizada e gravada com a lista de respostas vazia e status "concluida". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Alta          |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                 |
| -------------------------------------------------------------------- |
| 1. Acessar "Fichas Anamnese" e clicar em "Nova Anamnese".            |
| 2. Selecionar o aluno "Steven Kaiki".                                |
| 3. Selecionar o modelo "Triplet" (1 pergunta) e clicar em "Iniciar". |
| 4. Verificar se a pergunta é exibida.                                |

|                      **Comportamento Esperado**                       |                      **Comportamento Obtido**                       |
| :-------------------------------------------------------------------: | :-----------------------------------------------------------------: |
| A pergunta do modelo deve ser exibida para resposta antes da revisão. | O assistente pula para "Revisar e Finalizar" sem exibir a pergunta. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |        **Caso de Teste Relacionado**        |
| :----------------------------: | :-----------------------------------------: |
| Fichas de Anamnese / Aplicação | C18-CT05: Exibição das perguntas do modelo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:94](coloque o link do video aqui) |

---

### 🐞 **Bug 95: Assistente de anamnese avança sem aluno e falha com erro interno**

| **ID**  | **Descrição**                                                                                                                                                                                                           |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-095 | Ao clicar em "Próxima" sem selecionar aluno, o assistente avança para a escolha do modelo. Ao concluir o fluxo, o sistema exibe "Erro no servidor - Erro interno inesperado.", porque a anamnese foi enviada sem aluno. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Acessar "Fichas Anamnese" e clicar em "Nova Anamnese".                        |
| 2. Não selecionar aluno e clicar em "Próxima".                                   |
| 3. Selecionar o modelo "Triplet", clicar em "Iniciar" e em "Finalizar Anamnese". |
| 4. Verificar as mensagens exibidas.                                              |

|                            **Comportamento Esperado**                            |                   **Comportamento Obtido**                    |
| :------------------------------------------------------------------------------: | :-----------------------------------------------------------: |
| O sistema deve impedir o avanço e informar que é necessário selecionar um aluno. | O assistente avança e a finalização exibe "Erro no servidor". |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |      **Caso de Teste Relacionado**      |
| :----------------------------: | :-------------------------------------: |
| Fichas de Anamnese / Aplicação | C18-CT02: Avançar sem selecionar aluno. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:95](coloque o link do video aqui) |

---

### 🐞 **Bug 96: Nome do aluno não é exibido na escolha do modelo de anamnese**

| **ID**  | **Descrição**                                                                                                                                                                                         |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-096 | Na etapa "Selecionar Modelo", o texto é exibido como "Escolha o modelo de anamnese a aplicar para .", sem o nome do aluno selecionado, embora o aluno seja exibido no cabeçalho das etapas seguintes. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                      |
| --------------------------------------------------------- |
| 1. Acessar "Fichas Anamnese" e clicar em "Nova Anamnese". |
| 2. Selecionar o aluno "Steven Kaiki".                     |
| 3. Observar o texto da etapa "Selecionar Modelo".         |

|                            **Comportamento Esperado**                            |        **Comportamento Obtido**        |
| :------------------------------------------------------------------------------: | :------------------------------------: |
| O texto deve exibir "Escolha o modelo de anamnese a aplicar para Steven Kaiki.". | O texto é exibido sem o nome do aluno. |

| **Ambiente**                     |
| -------------------------------- |
| Endereço e data não registrados. |
| Google Chrome                    |

|   **Funcionalidade Afetada**   |           **Caso de Teste Relacionado**           |
| :----------------------------: | :-----------------------------------------------: |
| Fichas de Anamnese / Aplicação | C18-CT04: Exibição do aluno na escolha do modelo. |

|            **Evidência(s)**            |
| :------------------------------------: |
| [BUG:96](coloque o link do video aqui) |

---

### 🐞 **Bug 97: Filtro de período aceita data inicial maior que a final**

| **ID**  | **Descrição**                                                                                                                                         |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-097 | O filtro de período da Página Inicial aceita a data inicial 31/10/2026 com a data final 01/10/2026, sem aviso, e os cards continuam exibindo valores. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**        |
| ------------------------------------------- |
| 1. Acessar a Página Inicial do SIFIT.       |
| 2. Selecionar 31/10/2026 como data inicial. |
| 3. Selecionar 01/10/2026 como data final.   |
| 4. Observar os cards da página.             |

|                       **Comportamento Esperado**                       |                                    **Comportamento Obtido**                                    |
| :--------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------: |
| O sistema deve impedir a seleção ou informar que o período é inválido. | O período invertido é aceito sem aviso e os cards exibem dados (ex.: 2 matrículas no período). |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

|     **Funcionalidade Afetada**     |                  **Caso de Teste Relacionado**                  |
| :--------------------------------: | :-------------------------------------------------------------: |
| Página Inicial / Filtro de período | C02-CT09: Filtro de período com data inicial maior que a final. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:97](https://jam.dev/c/5f7f9e52-3989-42d5-99c2-66b747dec9e3) |

---

### 🐞 **Bug 98: Cadastro de cliente aceita data de nascimento futura**

| **ID**  | **Descrição**                                                                                                                       |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| BUG-098 | O cadastro de cliente aceita a data de nascimento 31/12/2027, posterior à data atual, e a ficha do cliente exibe a idade "-2 anos". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                     |
| -------------------------------------------------------- |
| 1. Acessar o formulário "Novo Cliente".                  |
| 2. Informar nome, status "Ativo" e sexo "Masculino".     |
| 3. Informar a data de nascimento 31/12/2027.             |
| 4. Clicar em "Cadastrar Cliente" e visualizar o cliente. |

|                              **Comportamento Esperado**                               |                 **Comportamento Obtido**                  |
| :-----------------------------------------------------------------------------------: | :-------------------------------------------------------: |
| O sistema deve rejeitar a data futura e informar que a data de nascimento é inválida. | O cliente é cadastrado e a ficha exibe a idade "-2 anos". |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |                **Caso de Teste Relacionado**                 |
| :------------------------: | :----------------------------------------------------------: |
|    Clientes / Cadastro     | C04-CT12: Cadastro de cliente com data de nascimento futura. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:98](https://jam.dev/c/f3cd80a9-c549-4e43-8957-182eaa983f3d) |

---

### 🐞 **Bug 99: CPF inválido é aceito no cadastro de cliente**

| **ID**  | **Descrição**                                                                                            |
| ------- | -------------------------------------------------------------------------------------------------------- |
| BUG-099 | O cadastro e a alteração de cliente aceitam o CPF "111.111.111-11", sem validação do dígito verificador. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                     |
| -------------------------------------------------------- |
| 1. Acessar o cadastro ou a alteração de um cliente.      |
| 2. Informar o CPF "111.111.111-11".                      |
| 3. Clicar em "Cadastrar Cliente" ou "Salvar Alterações". |

|                      **Comportamento Esperado**                       |         **Comportamento Obtido**         |
| :-------------------------------------------------------------------: | :--------------------------------------: |
| O sistema deve informar que o CPF é inválido e não salvar o cadastro. | O CPF inválido é salvo sem nenhum aviso. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

|   **Funcionalidade Afetada**    |          **Caso de Teste Relacionado**          |
| :-----------------------------: | :---------------------------------------------: |
| Clientes / Cadastro e alteração | C04-CT13: Cadastro de cliente com CPF inválido. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:99](https://jam.dev/c/aee4435d-fdbd-4a84-bfe5-d8a28801ecd7) |

---

### 🐞 **Bug 100: Filtro de status "Ativo" lista clientes inativos**

| **ID**  | **Descrição**                                                                               |
| ------- | ------------------------------------------------------------------------------------------- |
| BUG-100 | Com o filtro "Status" em "Ativo", a listagem de clientes exibe clientes com status INATIVO. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**        |
| ------------------------------------------- |
| 1. Acessar a listagem de clientes.          |
| 2. Manter o filtro "Status" em "Ativo".     |
| 3. Observar a coluna de status da listagem. |

|         **Comportamento Esperado**          |           **Comportamento Obtido**            |
| :-----------------------------------------: | :-------------------------------------------: |
| Somente clientes ativos devem ser listados. | A listagem exibe clientes com status INATIVO. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

|  **Funcionalidade Afetada**  |           **Caso de Teste Relacionado**           |
| :--------------------------: | :-----------------------------------------------: |
| Clientes / Filtro por status | C04-CT14: Filtro de clientes pelo status "Ativo". |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:100](https://jam.dev/c/a6adccf3-ae4c-47f8-9343-8ad793e5758e) |

---

### 🐞 **Bug 101: Ficha do cliente exibe "null" e objetivos fictícios**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                      |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-101 | A ficha de um cliente cadastrado sem telefone e sem endereço exibe o telefone como "null", o bairro como "null" na alteração e o card "Objetivos" com "Perda de peso e ganho de resistência" e "Progresso geral 60%", sem que esses dados tenham sido cadastrados. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                   |
| ---------------------------------------------------------------------- |
| 1. Cadastrar um cliente sem telefone e sem endereço.                   |
| 2. Acessar a listagem de clientes e clicar em "Visualizar" no cliente. |
| 3. Observar o telefone e o card "Objetivos".                           |
| 4. Clicar em "Editar" e observar o campo "Bairro".                     |

|                             **Comportamento Esperado**                             |                                           **Comportamento Obtido**                                           |
| :--------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------: |
| Os campos sem informação devem aparecer em branco ou com "-", sem dados fictícios. | O telefone e o bairro aparecem como "null", e o card "Objetivos" exibe objetivo e progresso não cadastrados. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |                **Caso de Teste Relacionado**                 |
| :------------------------: | :----------------------------------------------------------: |
|  Clientes / Visualização   | C04-CT15: Visualização da ficha de cliente recém-cadastrado. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:101](https://jam.dev/c/a4c73bde-5ac1-43ad-8a47-3ebde1f4e346) |

---

### 🐞 **Bug 102: Campo "Data" da parcela aceita data inválida**

| **ID**  | **Descrição**                                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------------------------- |
| BUG-102 | O campo "Data" da janela "Quantidade Parcelas", exibida ao salvar a matrícula, aceita a data inválida "2026/05/192". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                        |
| --------------------------------------------------------------------------- |
| 1. Acessar o formulário "Nova Matrícula" e preencher os dados.              |
| 2. Clicar em "Salvar".                                                      |
| 3. Na janela "Quantidade Parcelas", informar "2026/05/192" no campo "Data". |

|                  **Comportamento Esperado**                   |        **Comportamento Obtido**         |
| :-----------------------------------------------------------: | :-------------------------------------: |
| Somente datas válidas no padrão DD/MM/AAAA devem ser aceitas. | A data inválida "2026/05/192" é aceita. |

| **Ambiente**                  |
| ----------------------------- |
| https://sifit.centrion.com.br |
| Desktop com Windows 11.       |
| Google Chrome 155             |
| 23/10/2026 a 24/10/2026       |

| **Funcionalidade Afetada** |          **Caso de Teste Relacionado**           |
| :------------------------: | :----------------------------------------------: |
|   Matrículas / Parcelas    | C06-CT13: Data inválida na parcela da matrícula. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:102](https://jam.dev/c/02ee32cf-7b68-4011-9cd9-d0faaba8470e) |

---

### 🐞 **Bug 103: Sistema permite cadastrar grupo duplicado**

| **ID**  | **Descrição**                                                                                                                                                                           |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-103 | Foi possível cadastrar mais de uma vez o grupo "Grupo Teste Ville" (códigos #11, #12 e #13), sem nenhum aviso. Como grupos não podem ser excluídos (BUG-105), a duplicidade não pode ser corrigida. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                |
| ------------------------------------------------------------------- |
| 1. Acessar a tela "Grupos" do SIFIT.                                |
| 2. Cadastrar o grupo "Grupo Teste Ville".                           |
| 3. Clicar novamente no botão de novo grupo e informar o mesmo nome. |
| 4. Clicar no botão "Salvar Grupo".                                  |

|           **Comportamento Esperado**           |       **Comportamento Obtido**       |
| :--------------------------------------------: | :----------------------------------: |
| O sistema deve informar que o grupo já existe. | O grupo é cadastrado em duplicidade. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |     **Caso de Teste Relacionado**      |
| :------------------------: | :------------------------------------: |
|     Grupos / Cadastro      | C20-CT07: Cadastro de grupo duplicado. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:103](https://jam.dev/c/96a9fe9b-5a85-45a2-9798-159a31ea714b) |

---

### 🐞 **Bug 104: Status "Inativo" do grupo não é salvo**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-104 | Ao alterar o status de um grupo para "Inativo" e salvar, a tela envia "status": "inativo" e a API responde sem erro, mas o grupo continua "ATIVO" e o indicador "Ativos" não muda. O mesmo ocorre ao cadastrar um grupo novo como "Inativo". Os outros campos (nome e Mostrar Home) são salvos normalmente. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**          |
| --------------------------------------------- |
| 1. Acessar a tela "Grupos" do SIFIT.          |
| 2. Clicar no botão de visualizar de um grupo. |
| 3. Selecionar "Inativo" no campo "Status".    |
| 4. Clicar no botão "Salvar Grupo".            |
| 5. Verificar o status do grupo na listagem.   |

|                           **Comportamento Esperado**                           |               **Comportamento Obtido**               |
| :----------------------------------------------------------------------------: | :--------------------------------------------------: |
| O grupo deve constar como "INATIVO" e o indicador "Ativos" deve diminuir em 1. | O grupo continua "ATIVO" e os indicadores não mudam. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado**  |
| :------------------------: | :----------------------------: |
|     Grupos / Alteração     | C20-CT09: Inativação de grupo. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:104](https://jam.dev/c/98c0d5c7-f010-434f-a6ea-d44ddb49ffbb) |

---

### 🐞 **Bug 105: Grupo não pode ser excluído**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                       |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-105 | Ao confirmar a mensagem "Deseja deletar o Grupo?", aparece a mensagem "Erro ao deletar Grupo" e o grupo continua na listagem. No DevTools (aba Network), a exclusão retorna erro 500 com "Erro interno inesperado.". Ocorreu com grupos recém-criados, sem nenhum vínculo. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                |
| --------------------------------------------------- |
| 1. Acessar a tela "Grupos" do SIFIT.                |
| 2. Clicar no botão de excluir de um grupo de teste. |
| 3. Clicar em "Confirmar".                           |
| 4. Verificar a listagem.                            |

|                 **Comportamento Esperado**                 |                  **Comportamento Obtido**                  |
| :--------------------------------------------------------: | :--------------------------------------------------------: |
| O grupo deve ser excluído e deixar de constar na listagem. | Aparece "Erro ao deletar Grupo" e o grupo continua. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
|     Grupos / Exclusão      |  C20-CT10: Exclusão de grupo. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:105](https://jam.dev/c/e30de4bd-5de2-4dfb-87a2-f09bab3a8440) |

---

### 🐞 **Bug 106: Listagem de modelos de contrato aparece vazia**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                      |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-106 | A tela "Modelos Contrato" exibe só os títulos das colunas, mas a API retorna 9 modelos cadastrados. No HTML da tabela, cada modelo aparece como um elemento "corpo-modelo" sem conteúdo, o que indica que o componente da linha não é carregado. Sem a listagem, não é possível visualizar, alterar nem excluir modelos pela tela. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|          Alta         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                            |
| ------------------------------------------------------------------------------- |
| 1. Acessar o menu "Modelos Contrato".                                           |
| 2. Observar a listagem.                                                         |
| 3. Abrir o DevTools (aba Network) e conferir a resposta da listagem de modelos. |

|                           **Comportamento Esperado**                          |                  **Comportamento Obtido**                  |
| :---------------------------------------------------------------------------: | :--------------------------------------------------------: |
| A listagem deve exibir o código, o nome e o status de cada modelo cadastrado. | A listagem aparece vazia, embora a API retorne os modelos. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|   **Funcionalidade Afetada**   |                                          **Caso de Teste Relacionado**                                          |
| :----------------------------: | :-------------------------------------------------------------------------------------------------------------: |
| Modelos de contrato / Listagem | C21-CT01: Acesso à listagem de modelos de contrato. C21-CT06: Cadastro de modelo de contrato com dados válidos. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:106](https://jam.dev/c/e1e3d8bf-996d-4aaa-9868-e8f046bfdf01) |
| [Vídeo](https://jam.dev/c/fa52093b-2cba-4328-9ce9-fa00a0af85d5)   |

---

### 🐞 **Bug 107: Modelo de contrato é salvo sem texto**

| **ID**  | **Descrição**                                                                                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-107 | O cadastro de modelo de contrato exige o título, mas aceita salvar com o texto do contrato vazio. O modelo "Contrato Teste Ville" foi salvo sem texto (código 8). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**         |
| -------------------------------------------- |
| 1. Clicar em "Adicionar Modelo Contrato".    |
| 2. Informar o título "Contrato Teste Ville". |
| 3. Deixar o texto do contrato vazio.         |
| 4. Clicar em "Salvar modelo".                |

|                   **Comportamento Esperado**                   |   **Comportamento Obtido**  |
| :------------------------------------------------------------: | :-------------------------: |
| O sistema deve informar que o texto do contrato é obrigatório. | O modelo é salvo sem texto. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|   **Funcionalidade Afetada**   |         **Caso de Teste Relacionado**          |
| :----------------------------: | :--------------------------------------------: |
| Modelos de contrato / Cadastro | C21-CT03: Salvar modelo de contrato sem texto. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:107](https://jam.dev/c/648e27ae-8a17-496f-9886-1925dd6fc62a) |

---

### 🐞 **Bug 108: Box - Turmas não avisa nada ao salvar modalidade ou turma vazia**

| **ID**  | **Descrição**                                                                                                                                                                      |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-108 | Na tela "Box - Turmas", ao clicar em "Modalidade" ou em "Turma" com os campos vazios, o registro não é salvo, mas nenhuma mensagem orienta o usuário sobre os campos obrigatórios. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                 |
| ---------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                    |
| 2. Sem preencher nada, clicar no botão "Modalidade". |
| 3. Sem preencher nada, clicar no botão "Turma".      |

|            **Comportamento Esperado**           |           **Comportamento Obtido**          |
| :---------------------------------------------: | :-----------------------------------------: |
| O sistema deve informar os campos obrigatórios. | Nada acontece e nenhuma mensagem é exibida. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |                  **Caso de Teste Relacionado**                   |
| :------------------------: | :--------------------------------------------------------------: |
|  Box - Turmas / Cadastro   | C22-CT02: Salvar modalidade vazia. C22-CT06: Salvar turma vazia. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:108 - modalidade](https://jam.dev/c/bbce3086-ea71-4f96-984f-30bece9b67e4) |
| [BUG:108 - turma](https://jam.dev/c/3587cecb-d159-4fcb-9c58-534e9430bcea) |

---

### 🐞 **Bug 109: Erro 500 e mensagem genérica ao cadastrar modalidade duplicada**

| **ID**  | **Descrição**                                                                                                                                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-109 | Ao cadastrar uma modalidade com o nome de uma já existente ("Modalidade Teste Ville"), a modalidade não é duplicada, mas a tela mostra só a mensagem genérica "Erro ao salvar modalidade", sem informar que o nome já existe. No DevTools (aba Network), a API retorna erro 500 com "Erro interno inesperado.". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                             |
| ---------------------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                                |
| 2. Cadastrar a modalidade "Modalidade Teste Ville".              |
| 3. Informar de novo o mesmo nome e clicar no botão "Modalidade". |
| 4. Observar a tela e a aba Network do DevTools.                  |

|              **Comportamento Esperado**             |               **Comportamento Obtido**               |
| :-------------------------------------------------: | :--------------------------------------------------: |
| O sistema deve informar que a modalidade já existe. | Aparece "Erro ao salvar modalidade" e a API retorna erro 500. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |        **Caso de Teste Relacionado**        |
| :------------------------: | :-----------------------------------------: |
| Box - Turmas / Modalidades | C22-CT04: Cadastro de modalidade duplicada. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:109](https://jam.dev/c/b66fe3ca-342c-4605-9fa7-10417c54e174) |

---

### 🐞 **Bug 110: Turma do Box aceita hora final anterior à hora inicial**

| **ID**  | **Descrição**                                                                                                                                          |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-110 | O sistema permite cadastrar uma turma do Box com hora inicial 11:00 e hora final 10:00. A turma é salva e exibida com o horário "11:00:00 - 10:00:00". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                    |
| ----------------------------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                                       |
| 2. Informar o nome "Turma Box Ville Horario", a modalidade e o dia Ter. |
| 3. Informar a hora inicial 11:00 e a hora final 10:00.                  |
| 4. Clicar no botão "Turma".                                             |

|                          **Comportamento Esperado**                         |                  **Comportamento Obtido**                 |
| :-------------------------------------------------------------------------: | :-------------------------------------------------------: |
| O sistema deve informar que a hora final deve ser maior que a hora inicial. | A turma é cadastrada com o horário "11:00:00 - 10:00:00". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |                 **Caso de Teste Relacionado**                  |
| :------------------------: | :------------------------------------------------------------: |
|   Box - Turmas / Turmas    | C22-CT08: Cadastro de turma com hora final anterior à inicial. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:110](https://jam.dev/c/005742d4-d9e7-4724-8363-f5636b983438) |

---

### 🐞 **Bug 111: Turma do Box é cadastrada sem dias da semana**

| **ID**  | **Descrição**                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-111 | O sistema permite cadastrar uma turma recorrente do Box sem nenhum dia da semana selecionado. A turma "Turma Box Ville Sem Dia" foi salva sem dias de aula. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                   |
| ------------------------------------------------------ |
| 1. Acessar o menu "Box - Turmas".                      |
| 2. Informar o nome, a modalidade e o horário da turma. |
| 3. Não selecionar nenhum dia da semana.                |
| 4. Clicar no botão "Turma".                            |

|            **Comportamento Esperado**            |       **Comportamento Obtido**       |
| :----------------------------------------------: | :----------------------------------: |
| O sistema deve exigir ao menos um dia da semana. | A turma é cadastrada sem nenhum dia. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |          **Caso de Teste Relacionado**          |
| :------------------------: | :---------------------------------------------: |
|   Box - Turmas / Turmas    | C22-CT09: Cadastro de turma sem dias da semana. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:111](https://jam.dev/c/b504ede6-2ed2-4caf-9c94-a83e4702866c) |

---

### 🐞 **Bug 112: Turma do Box aceita quantidade de vagas negativa**

| **ID**  | **Descrição**                                                                                                                  |
| ------- | ------------------------------------------------------------------------------------------------------------------------------ |
| BUG-112 | O campo de vagas da turma do Box aceita valor negativo. A turma "Turma Box Ville Vagas" foi cadastrada e listada com -5 vagas. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                            |
| --------------------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                               |
| 2. Informar o nome, a modalidade e um dia da semana.            |
| 3. Informar -5 no campo de vagas.                               |
| 4. Clicar no botão "Turma".                                     |

|                     **Comportamento Esperado**                     |      **Comportamento Obtido**      |
| :----------------------------------------------------------------: | :--------------------------------: |
| O sistema deve aceitar somente quantidade de vagas maior que zero. | A turma é cadastrada com -5 vagas. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |          **Caso de Teste Relacionado**           |
| :------------------------: | :----------------------------------------------: |
|   Box - Turmas / Turmas    | C22-CT10: Cadastro de turma com vagas negativas. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:112](https://jam.dev/c/24af9192-9c04-47b9-8937-7641f4446a78) |

---

### 🐞 **Bug 113: Modalidade inativa aparece no cadastro de turma do Box**

| **ID**  | **Descrição**                                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-113 | O campo "Modalidade" do cadastro de turma lista a modalidade inativa "Leo valesk", e a turma "Turma Box Ville Vagas" foi cadastrada com ela. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                    |
| ------------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                       |
| 2. Conferir que a modalidade "Leo valesk" está inativa. |
| 3. Abrir o campo "Modalidade" do cadastro de turma.     |

|            **Comportamento Esperado**           |            **Comportamento Obtido**            |
| :---------------------------------------------: | :--------------------------------------------: |
| O campo deve listar somente modalidades ativas. | A modalidade inativa aparece e pode ser usada. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |            **Caso de Teste Relacionado**            |
| :------------------------: | :-------------------------------------------------: |
|   Box - Turmas / Turmas    | C22-CT11: Cadastro de turma com modalidade inativa. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:113](https://jam.dev/c/e12097b4-c4db-4d08-9cf7-372201929e55) |

---

### 🐞 **Bug 114: Exclusão de turma do Box não pede confirmação e mantém a turma na lista**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                      |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-114 | Ao clicar no botão de excluir de uma turma do Box, a ação é executada na hora, sem confirmação, e os dados da turma são carregados no formulário com o status "Inativo". A API responde sem erro, mas a turma continua na listagem: pela API, ela só passa para "inativo", e a listagem não tem coluna de status. O mesmo ocorre com modalidades, que ficam como "inativo". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                 |
| ---------------------------------------------------- |
| 1. Acessar o menu "Box - Turmas".                    |
| 2. Clicar no botão de excluir de uma turma de teste. |
| 3. Observar se há confirmação.                       |
| 4. Verificar a listagem de turmas.                   |

|                    **Comportamento Esperado**                   |              **Comportamento Obtido**              |
| :-------------------------------------------------------------: | :------------------------------------------------: |
| O sistema deve pedir confirmação e retirar a turma da listagem. | Não há confirmação e a turma continua na listagem. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
|  Box - Turmas / Exclusão   |  C22-CT13: Exclusão de turma. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:114](https://jam.dev/c/b1f29d33-a1f6-45c6-a289-8aa62f3d39a6) |

---

### 🐞 **Bug 115: Janela "Alterar Data / Hora" aceita data e hora sem formato**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                         |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-115 | Na janela "Alterar Data / Hora" da avaliação, os campos "Nova Data" e "Nova Hora" aceitam "101010" e "1411", sem máscara e sem validação. Ao clicar em "Salvar", nada acontece e nenhuma mensagem é exibida. Os valores digitados continuam nos campos ao abrir a janela de outra avaliação (Marcelo Longo Zandonadi e Raquel Dodge). |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                               |
| ------------------------------------------------------------------ |
| 1. Acessar a tela Avaliações com o filtro Pendente.                |
| 2. Clicar em "Alterar" da avaliação de Manual SIFIT Aluno Exemplo. |
| 3. Informar "101010" em "Nova Data" e "1411" em "Nova Hora".       |
| 4. Clicar em "Salvar" e depois em "Cancelar".                      |
| 5. Clicar em "Alterar" de outra avaliação.                         |

|                                                             **Comportamento Esperado**                                                              |                                                          **Comportamento Obtido**                                                          |
| :-------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------: |
| Os campos devem aceitar só data no padrão DD/MM/AAAA e hora no padrão HH:MM, com mensagem para valor inválido, e abrir vazios na próxima avaliação. | Os valores inválidos são aceitos, "Salvar" não faz nada nem mostra mensagem, e "101010" e "1411" aparecem na janela das outras avaliações. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 150.0.7871.46        |
| 15/11/2026                         |

|      **Funcionalidade Afetada**       |                **Caso de Teste Relacionado**                |
| :-----------------------------------: | :---------------------------------------------------------: |
| Avaliações / Alteração de data e hora | C10-CT12: Alteração da avaliação com data e hora inválidas. |

|                         **Evidência(s)**                          |
| :---------------------------------------------------------------: |
| [BUG:115](https://jam.dev/c/e7b3f5ff-5bd1-4fde-be72-0c33ebfac152) |

---

### 🐞 **Bug 116: Telas de bancos e de categorias de conta a pagar não estão no menu**

| **ID**  | **Descrição**                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-116 | As telas Bancos, Banco Recorrente e Categorias de Conta a Pagar não aparecem no menu lateral. Elas só abrem pelo link, e Bancos e Categorias abrem sem o menu lateral. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |           Média            |   Aberto   |

| **Passo a passo para simular o bug**                                                      |
| ----------------------------------------------------------------------------------------- |
| 1. Acessar o SIFIT autenticado.                                                           |
| 2. Procurar "Bancos", "Banco Recorrente" e "Categorias" de conta a pagar no menu lateral. |
| 3. Abrir https://sifitalfa.centrion.com.br/bancos pelo link.                              |

|    **Comportamento Esperado**    |              **Comportamento Obtido**             |
| :------------------------------: | :-----------------------------------------------: |
| As telas devem ter item no menu. | Não há item no menu; as telas só abrem pelo link. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|      **Funcionalidade Afetada**      |                                    **Caso de Teste Relacionado**                                    |
| :----------------------------------: | :-------------------------------------------------------------------------------------------------: |
| Bancos / Categorias de conta a pagar | C30-CT01: Acesso às telas de bancos pelo menu. C31-CT01: Acesso à tela Categorias de Conta a Pagar. |

|                                **Evidência(s)**                                |
| :----------------------------------------------------------------------------: |
|   [BUG:116 - bancos](https://jam.dev/c/a7570689-c2c4-46f2-b064-c9b9a0030a0b)   |
| [BUG:116 - categorias](https://jam.dev/c/5fe27a74-c994-4c78-9906-aaae1ba17b39) |

---

### 🐞 **Bug 117: Banco é salvo sem nome**

| **ID**  | **Descrição**                                                                                                      |
| ------- | ------------------------------------------------------------------------------------------------------------------ |
| BUG-117 | Na tela Bancos, ao clicar em "Salvar" com os campos vazios, nenhuma mensagem aparece e um banco sem nome é criado. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**               |
| -------------------------------------------------- |
| 1. Abrir https://sifitalfa.centrion.com.br/bancos. |
| 2. Sem preencher nada, clicar em "Salvar".         |
| 3. Olhar a listagem.                               |

|            **Comportamento Esperado**           |   **Comportamento Obtido**  |
| :---------------------------------------------: | :-------------------------: |
| O sistema deve avisar que o nome é obrigatório. | Um banco sem nome é criado. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
|     Bancos / Cadastro      | C30-CT03: Salvar banco vazio. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:117](https://jam.dev/c/76f082bc-40ee-47db-aaeb-0d181408c68c) |

---

### 🐞 **Bug 118: Banco duplicado é aceito**

| **ID**  | **Descrição**                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------- |
| BUG-118 | O sistema deixa cadastrar de novo um banco com o mesmo nome e código ("Banco Teste Ville", 999), sem nenhuma mensagem. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                       |
| ---------------------------------------------------------- |
| 1. Abrir https://sifitalfa.centrion.com.br/bancos.         |
| 2. Cadastrar o banco "Banco Teste Ville" com o código 999. |
| 3. Cadastrar de novo o mesmo nome e código.                |

|          **Comportamento Esperado**          |         **Comportamento Obtido**        |
| :------------------------------------------: | :-------------------------------------: |
| O sistema deve avisar que o banco já existe. | O banco aparece duas vezes na listagem. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** |     **Caso de Teste Relacionado**      |
| :------------------------: | :------------------------------------: |
|     Bancos / Cadastro      | C30-CT05: Cadastro de banco duplicado. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:118](https://jam.dev/c/f1723af8-3f46-4586-8c15-340990fd857a) |

---

### 🐞 **Bug 119: Excluir banco chama a exclusão de tipo de pagamento**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                             |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-119 | Na tela Bancos, o X de excluir pergunta "Deseja deletar o Tipo de Pagamento?". Ao confirmar, aparece "Erro ao deletar tipo de pagamento" e o banco continua na lista. A tela envia o código do banco para a exclusão de tipo de pagamento (/deleta/tipo-pagamento): se o tipo de pagamento com o mesmo código não estiver em uso, ele pode ser apagado no lugar do banco. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|        Crítica        |          Crítica           |   Aberto   |

| **Passo a passo para simular o bug**               |
| -------------------------------------------------- |
| 1. Abrir https://sifitalfa.centrion.com.br/bancos. |
| 2. Clicar no X do banco "Banco Brasil".            |
| 3. Ler a mensagem e clicar em "Confirmar".         |

|                **Comportamento Esperado**               |                                              **Comportamento Obtido**                                             |
| :-----------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------: |
| A confirmação deve falar do banco e excluir só o banco. | A confirmação fala de Tipo de Pagamento, aparece "Erro ao deletar tipo de pagamento" e o banco continua na lista. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
|     Bancos / Exclusão      |  C30-CT07: Exclusão de banco. |

|             **Evidência(s)**            |
| :-------------------------------------: |
| [BUG:119](https://jam.dev/c/6849358c-8f8d-44ce-96f5-e1ae38ec4006) |

---

### 🐞 **Bug 120: Listagem de categorias de conta a pagar aparece vazia**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-120 | A tela Categorias de Conta a Pagar mostra a tabela vazia, só com os títulos das colunas. No DevTools (aba Network), a API /categoria-contas-pagar retorna as categorias cadastradas (ex.: "Contas do dia a dia"), que aparecem no campo "Categoria" da conta a pagar. Sem a listagem, não há como alterar nem excluir categorias. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|          Alta         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                 |
| -------------------------------------------------------------------- |
| 1. Acessar https://sifitalfa.centrion.com.br/categorias-conta-pagar. |
| 2. Observar a listagem.                                              |
| 3. Conferir a resposta da API na aba Network do DevTools.            |

|                      **Comportamento Esperado**                      |                  **Comportamento Obtido**                  |
| :------------------------------------------------------------------: | :--------------------------------------------------------: |
| A listagem deve exibir o código e o nome das categorias cadastradas. | A listagem fica vazia, embora a API retorne as categorias. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|       **Funcionalidade Afetada**       |   **Caso de Teste Relacionado**   |
| :------------------------------------: | :-------------------------------: |
| Categorias de conta a pagar / Listagem | C31-CT02: Listagem de categorias. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:120](https://jam.dev/c/8803140b-f4b4-4e45-b612-a4bb026a45ac) |

---

### 🐞 **Bug 121: Categoria de conta a pagar é salva sem nome**

| **ID**  | **Descrição**                                                                                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-121 | Na tela Categorias de Conta a Pagar, ao clicar em "Salvar" com o nome vazio, nenhuma mensagem aparece e uma categoria sem nome é criada. Ela aparece como opção em branco no campo "Categoria" da conta a pagar. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                               |
| ------------------------------------------------------------------ |
| 1. Abrir https://sifitalfa.centrion.com.br/categorias-conta-pagar. |
| 2. Sem preencher o nome, clicar em "Salvar".                       |
| 3. Em Contas a Pagar → Nova Conta, abrir o campo "Categoria".      |

|            **Comportamento Esperado**           |                          **Comportamento Obtido**                         |
| :---------------------------------------------: | :-----------------------------------------------------------------------: |
| O sistema deve avisar que o nome é obrigatório. | Uma categoria sem nome é criada e aparece em branco no campo "Categoria". |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|       **Funcionalidade Afetada**       |   **Caso de Teste Relacionado**   |
| :------------------------------------: | :-------------------------------: |
| Categorias de conta a pagar / Cadastro | C31-CT03: Salvar categoria vazia. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:121](https://jam.dev/c/9e6b78ae-531e-49b3-8b84-15cf25b861f1) |

---

### 🐞 **Bug 122: Categoria de conta a pagar duplicada é aceita**

| **ID**  | **Descrição**                                                                                                                                                                                                                          |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-122 | O sistema permite cadastrar de novo a categoria "Categoria Teste Ville" (categoria 29), sem nenhuma mensagem. O campo "Categoria" da conta a pagar já mostra nomes repetidos: "Boleto" 4 vezes, "Pix" 6 vezes e "Pix Sicredi" 5 vezes. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Baixa         |           Baixa            |   Aberto   |

| **Passo a passo para simular o bug**                                 |
| -------------------------------------------------------------------- |
| 1. Acessar https://sifitalfa.centrion.com.br/categorias-conta-pagar. |
| 2. Cadastrar a categoria "Categoria Teste Ville".                    |
| 3. Informar de novo o mesmo nome e clicar em "Salvar".               |
| 4. Abrir o campo "Categoria" em Contas a Pagar → Nova Conta.         |

|             **Comportamento Esperado**             |                      **Comportamento Obtido**                      |
| :------------------------------------------------: | :----------------------------------------------------------------: |
| O sistema deve informar que a categoria já existe. | A categoria é cadastrada de novo e o campo mostra nomes repetidos. |

| **Ambiente**                       |
| ---------------------------------- |
| Sifit Unialfa                      |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS           |
| Google Chrome 155.0.8059.84        |
| 15/11/2026                         |

|       **Funcionalidade Afetada**       |       **Caso de Teste Relacionado**        |
| :------------------------------------: | :----------------------------------------: |
| Categorias de conta a pagar / Cadastro | C31-CT05: Cadastro de categoria duplicada. |

|                          **Evidência(s)**                         |
| :---------------------------------------------------------------: |
| [BUG:122](https://jam.dev/c/4f5e6f3b-1d3d-4ecf-88a2-40e3019b5a2c) |
