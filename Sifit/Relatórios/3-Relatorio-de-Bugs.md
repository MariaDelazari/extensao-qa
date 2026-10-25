# Relatório de Bugs

**Software:** Sifit Centrion

**QA responsável:** Maria Eduarda Pacheco Delazari

**Data:** 12.10.26

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

| **Funcionalidade Afetada** |               **Caso de Teste Relacionado**               |
| :------------------------: | :-------------------------------------------------------: |
|    Login / Autenticação    | C01-CT04: Login com credenciais válidas e espaços extras. |

|                         **Evidência(s)**                        |
| :-------------------------------------------------------------: |
| [BUG:01](https://jam.dev/c/51531b19-254b-468b-ad89-7487194fc22a) |

---

### 🐞 **Bug 02: Link "Esqueci minha senha" não funciona**

| **ID**  | **Descrição**                                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-002 | Ao clicar no link "Esqueci minha senha" na tela de login, o sistema não realiza nenhum redirecionamento, impedindo o acesso à funcionalidade de recuperação de senha. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|         Média         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                             |
| -------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                    |
| 2. Localizar o link "Esqueci minha senha".                                       |
| 3. Clicar no link.                                                               |
| 4. Verificar se ocorre o redirecionamento para a página de recuperação de senha. |

|                                          **Comportamento Esperado**                                         |                                     **Comportamento Obtido**                                    |
| :---------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| O sistema deve direcionar o usuário para a página de recuperação de senha ao clicar no link correspondente. | Ao clicar no link, nenhum redirecionamento é realizado, e o usuário permanece na tela de login. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|  **Funcionalidade Afetada**  |       **Caso de Teste Relacionado**       |
| :--------------------------: | :---------------------------------------: |
| Login / Recuperação de senha | C01-CT07: Acessar a recuperação de senha. |

|                         **Evidência(s)**                        |
| :-------------------------------------------------------------: |
| [BUG:02](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

---

### 🐞 **Bug 03: Erro interno do servidor ao validar credenciais inválidas no login**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-003 | Ao inserir uma senha incorreta na tela de login, a requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.". A resposta da API contém `"verifica_erro": true`, indicando uma falha, mas não identifica o problema como credenciais inválidas. O sistema deveria tratar a tentativa como uma falha de autenticação e apresentar uma mensagem clara ao usuário. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|          Alta         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                                                  |
| --------------------------------------------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                                                         |
| 2. Inserir um nome de usuário válido.                                                                                 |
| 3. Inserir uma senha incorreta.                                                                                       |
| 4. Clicar no botão verde "Entrar".                                                                                    |
| 5. Verificar a resposta da requisição `POST /api/login` na aba Network das ferramentas de desenvolvedor do navegador. |

|                                                                                               **Comportamento Esperado**                                                                                               |                                                                                              **Comportamento Obtido**                                                                                             |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve validar as credenciais informadas e, caso sejam inválidas, retornar uma resposta apropriada de falha de autenticação, como "Nome de usuário ou senha inválidos", sem gerar um erro interno do servidor. | A requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.", em vez de informar que as credenciais estão incorretas. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

| **Funcionalidade Afetada** |       **Caso de Teste Relacionado**        |
| :------------------------: | :----------------------------------------: |
|    Login / Autenticação    | C01-CT02: Login com credenciais inválidas. |

|                         **Evidência(s)**                        |
| :-------------------------------------------------------------: |
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

|                                                                **Comportamento Esperado**                                                                |                                                                                                                                **Comportamento Obtido**                                                                                                                               |
| :------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| O sistema deve validar os campos obrigatórios antes de enviar a requisição, informando ao usuário que o nome de usuário e a senha devem ser preenchidos. | O sistema envia a requisição à API mesmo com os campos vazios. A API retorna uma resposta vazia (`[]`), e a mensagem padrão de credenciais inválidas aparece no console do navegador. A interface não informa que os campos são obrigatórios, e o usuário permanece na tela de login. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|        **Funcionalidade Afetada**        |                **Caso de Teste Relacionado**                 |
| :--------------------------------------: | :----------------------------------------------------------: |
| Login / Validação de campos obrigatórios | C01-CT03: Tentativa de login com campos obrigatórios vazios. |

|                         **Evidência(s)**                        |
| :-------------------------------------------------------------: |
| [BUG:04](https://jam.dev/c/fcd3f7a9-9e1b-4aa3-a683-f5155d753e53) |

---

### 🐞 **Bug 05: Falha na persistência e no controle da sessão de login**

| **ID**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-005 | Ao marcar a opção "Manter conectado" e retornar ao sistema Sifit, o usuário é redirecionado à tela de login e precisa informar suas credenciais novamente, mesmo tendo selecionado essa opção. Entretanto, ao permanecer na tela de login e inserir diretamente a URL `/dashboard` no navegador, o sistema permite o acesso à área autenticada sem solicitar novamente o login. Dessa forma, o sistema apresenta duas falhas: não mantém o usuário conectado conforme esperado e permite o acesso ao dashboard diretamente pela URL, sem exigir autenticação. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
|          Alta         |            Alta            |   Aberto   |

| **Passo a passo para simular o bug**                                                                        |
| ----------------------------------------------------------------------------------------------------------- |
| 1. Acessar a tela de login do sistema Sifit Centrion.                                                       |
| 2. Informar credenciais válidas nos campos de nome de usuário e senha.                                      |
| 3. Marcar a opção "Manter conectado".                                                                       |
| 4. Clicar no botão "Entrar" e abrir o sistema em uma nova aba do navegador.                                 |
| 5. Retornar à tela de login e verificar se o sistema solicita novamente as credenciais.                     |
| 6. Permanecer na tela de login e inserir diretamente a URL `/dashboard` na barra de endereços do navegador. |
| 7. Verificar se o sistema permite o acesso ao dashboard sem solicitar autenticação novamente.               |

|                                                                                                                                                                                                   **Comportamento Esperado**                                                                                                                                                                                                  |                                                                                                                                                                   **Comportamento Obtido**                                                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Ao marcar a opção "Manter conectado", o sistema deve manter a autenticação do usuário ao retornar à aplicação, conforme o comportamento esperado dessa funcionalidade. Caso o usuário não possua uma sessão válida, o sistema deve bloquear o acesso ao dashboard, inclusive quando a URL `/dashboard` for inserida diretamente na barra de endereços do navegador, redirecionando-o à tela de login e exigindo autenticação. | Ao marcar a opção "Manter conectado", o usuário é redirecionado à tela de login ao retornar ao sistema e precisa informar suas credenciais novamente. Entretanto, ao permanecer na tela de login e inserir diretamente a URL `/dashboard` na barra de endereços do navegador, o sistema permite o acesso à área autenticada sem solicitar novamente o login. |

| **Ambiente**                  |
| ----------------------------- |
| Ambiente de testes.           |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46   |
| Sifit Centrion.               |

|              **Funcionalidade Afetada**             |                         **Caso de Teste Relacionado**                         |
| :-------------------------------------------------: | :---------------------------------------------------------------------------: |
| Login / Persistência da sessão / Controle de acesso | C01-CT05: Manter conectado. C01-CT06: Acesso ao /dashboard sem sessão válida. |

|                         **Evidência(s)**                        |
| :-------------------------------------------------------------: |
| [BUG:05](https://jam.dev/c/0e862f82-e4d0-49df-9406-0ff970332873) |

---

### 🐞 **Bug 06 Login: Erro interno do servidor ao autenticar com credenciais válidas**

| **ID** | **Descrição** |
|---|---|
| BUG-006| Ao informar credenciais válidas na tela de login e tentar acessar o sistema, a requisição `POST /api/login` para o endpoint de autenticação retorna o status `500 Internal Server Error`. A resposta da API contém `"verifica_erro": true` e a mensagem `"Erro interno inesperado."`, impedindo a conclusão da autenticação. Dessa forma, o usuário não consegue acessar o sistema, mesmo informando as credenciais da conta de teste. |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a tela de login do sistema Sifit Centrion. |
| 2. Informar as credenciais válidas da conta de teste. |
| 3. Clicar no botão "Entrar". |
| 4. Abrir as ferramentas de desenvolvedor do navegador e acessar a aba Network. |
| 5. Localizar a requisição `POST /api/login` e verificar o status e o conteúdo da resposta. |
| 6. Verificar se a autenticação é concluída e se o usuário consegue acessar o sistema. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| Ao informar credenciais válidas, o sistema deve autenticar o usuário e permitir o acesso à aplicação, sem retornar erros internos do servidor. | A requisição `POST /api/login` retorna o status `500 Internal Server Error`. A resposta da API contém `"verifica_erro": true` e a mensagem `"Erro interno inesperado."`, impedindo a autenticação e o acesso ao sistema. |

| **Ambiente** |
|---|
| Ambiente de testes |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| Sifit Centrion |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Autenticação com credenciais válidas | C01-CT07 Login com credenciais válidas. |

| **Evidência(s)** |
|---|
| [BUG:06](https://jam.dev/c/070f284b-e3a2-4514-8fe3-4290f33d77ee) |


---

### 🐞 **Bug 07: Inconsistência na identificação do usuário e na autenticação**

| **ID** | **Descrição** |
|---|---|
| BUG-007 | Ao tentar realizar o login com o usuário `marcelo_zandonadi`, o sistema exibe a mensagem "O nome de usuário e senha não correspondem", impedindo a autenticação. Na mesma gravação, é exibido o perfil de um usuário identificado como Jair, porém não há informação visível no perfil que permita confirmar se esse nome está associado ao login utilizado na tentativa de autenticação. Dessa forma, não é possível confirmar a correspondência entre o usuário informado no login e o perfil apresentado no sistema. |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a tela de login do sistema Sifit Centrion. |
| 2. Informar o usuário `marcelo_zandonadi` e a senha da conta de teste. |
| 3. Clicar no botão "Entrar". |
| 4. Verificar a mensagem apresentada pelo sistema após a tentativa de autenticação. |
| 5. Acessar o perfil exibido na gravação e verificar os dados disponíveis sobre a identificação do usuário. |
| 6. Verificar se existe alguma informação que relacione o nome apresentado no perfil ao nome de usuário utilizado no login. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve permitir a autenticação quando as credenciais forem válidas e apresentar informações que permitam identificar corretamente o usuário autenticado. | A tentativa de login com `marcelo_zandonadi` é rejeitada com a mensagem "O nome de usuário e senha não correspondem". O perfil exibido posteriormente apresenta o nome Jair, mas não há informação visível que confirme sua relação com o login utilizado. |

| **Ambiente** |
|---|
| Ambiente de testes |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| Sifit Centrion |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Autenticação / Identificação do usuário | C02-CT01: Abrir a página inicial depois do login. |

| **Evidência(s)** |
|---|
| [BUG:07](https://jam.dev/c/ca20044a-89b1-4723-b121-2863cfb8d4a7). |
