# Relatório de Bugs

**Software:** Sifit Centrion

**Versão:** Sifit Centrion e Sifit Unialfa

**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, https://sifitalfa.centrion.com.br/

**QA responsável:** Maria Eduarda Pacheco Delazari

**Data:** 12.10.26. Em 24/10/2026, os testes continuaram no Sifit Unialfa. Os BUG-012 a BUG-033 foram observados em 28/10/2026.

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
| Login / Autenticação com credenciais válidas | C01-CT01: Login com credenciais válidas. |

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
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Autenticação / Identificação do usuário | C01-CT01: Login com credenciais válidas. C02-CT01: Abrir a página inicial depois do login. |

| **Evidência(s)** |
|---|
| [BUG:07](https://jam.dev/c/ca20044a-89b1-4723-b121-2863cfb8d4a7) |

---

### 🐞 **Bug 08: Radar de Evasão mostra a faixa errada de alunos**

| **ID** | **Descrição** |
|---|---|
| BUG-008 | No Sifit Unialfa, o detalhe "Radar de Evasão" informa no rodapé que está exibindo os alunos 3 a 4 de um total de 4. A tabela visível no mesmo quadro lista quatro alunos. O botão "Exportar relatório" é acionado várias vezes na gravação, sem mensagem de confirmação. |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard. |
| 2. Abrir o detalhe dos alunos em risco de evasão. |
| 3. Conferir o rodapé "Exibindo..." e a quantidade de linhas da tabela. |
| 4. Clicar em "Exportar relatório". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O rodapé deve indicar a faixa real de linhas visíveis. O exportar deve gerar o relatório ou avisar se não foi possível. | Em 25/10/2026, o rodapé aparece como "Exibindo 3 a 4 de 4 alunos em risco", com quatro linhas na tabela. A gravação não mostra o arquivo exportado nem um aviso. O Jam desse vídeo não trouxe registro de rede, então não dá para afirmar que a requisição deixou de sair. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 25/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Radar de Evasão | C02-CT02: Conferir os cards do resumo da academia. |

| **Evidência(s)** |
|---|
| [BUG:08](https://jam.dev/c/fa584de0-d641-465a-a2b3-d0a311bc1c5a) |

---

### 🐞 **Bug 09: Cobrança e perfil de Rafael Santos não fecham com a lista**

| **ID** | **Descrição** |
|---|---|
| BUG-009 | Na cobrança de Rafael Santos pelo WhatsApp, a tela mostra mensalidade de R$ 350,00 e multa de R$ 1,00, mas o total atualizado é R$ 375,59. A mensagem pronta repete esse total. Na mesma gravação, a lista de clientes mostra o aluno 398 com plano Treino Personal e status ATIVO, e o perfil dele mostra "Sem matrícula" e "Sem registros". |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard. |
| 2. Abrir a cobrança de Rafael Santos, vencimento 12/05/2026. |
| 3. Comparar valor, multa e total atualizado na janela "Cobrar via WhatsApp". |
| 4. Abrir Clientes, localizar o código 398 e entrar em Visualizar Cliente. |
| 5. Comparar plano e matrícula da lista com os do perfil. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O total da cobrança deve ser a soma dos valores apresentados, ou a tela deve mostrar a parcela que falta. O plano e a matrícula do perfil devem ser os mesmos da lista. | O total fica em R$ 375,59, e a multa exibida é R$ 1,00. A lista diz Treino Personal e ATIVO. O perfil diz Sem matrícula, 0/3 aulas e sem registros. O vencimento visto no perfil é 08/07/2026. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 25/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Cobrança e cadastro do aluno | C02-CT02: Conferir os cards do resumo da academia. |

| **Evidência(s)** |
|---|
| [BUG:09](https://jam.dev/c/cca56c7a-000b-43b7-9fb8-2012e445ee9a) |

---

### 🐞 **Bug 10: Card de valor em aberto não confere com o detalhe**

| **ID** | **Descrição** |
|---|---|
| BUG-010 | Na página inicial do Sifit Unialfa, o card mostra R$ 200,00 em aberto. Ao abrir "Financeiro em Aberto", o total exibido é R$ 450,00. A linha de Rafael Santos mostra R$ 350,00 e um acréscimo de R$ 100,00. |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard. |
| 2. Anotar o valor do card "em aberto". |
| 3. Abrir o detalhe Financeiro em Aberto. |
| 4. Comparar o total do detalhe, a quantidade de alunos em atraso e o valor da linha de Rafael Santos. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O total do detalhe deve ser o mesmo valor do card, e a soma das linhas deve explicar esse total. | O card mostra R$ 200,00. O detalhe mostra R$ 450,00, com 2 alunos em atraso e 8 mensalidades. A linha visível de Rafael Santos está em R$ 350,00, com +R$ 100,00. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/dashboard |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 25/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Mensalidades em aberto | C02-CT02: Conferir os cards do resumo da academia. |

| **Evidência(s)** |
|---|
| [BUG:10](https://jam.dev/c/63ec10f5-e5b6-4150-a1f6-8e0c1978f806) |

---

### 🐞 **Bug 11: O campo de senha não deixa ver o que foi digitado**

| **ID** | **Descrição** |
|---|---|
| BUG-011 | Na tela de login, o campo de senha não tem ícone nem outra opção para mostrar os caracteres. A pessoa não consegue conferir a senha antes de clicar em Entrar. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Abrir a tela de login. |
| 2. Clicar no campo de senha. |
| 3. Digitar uma senha. |
| 4. Procurar um ícone ou botão para mostrar o que foi digitado. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O campo deve ter um controle para mostrar e esconder a senha, para a pessoa conferir o que digitou antes de entrar. | A senha fica oculta o tempo todo. Não há controle para exibi-la. |

| **Ambiente** |
|---|
| Sifit Centrion |
| Desktop com Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Campo de senha | C01-CT01: Login com credenciais válidas. |

| **Evidência(s)** |
|---|
| [BUG:11](https://jam.dev/c/1c6d4e56-7c8b-43d3-9134-c3bde64d0d80) |

---

### 🐞 **Bug 12: Dashboard mostra o título "Despesas Fixas"**

| **ID** | **Descrição** |
|---|---|
| BUG-012 | Ao abrir a página Dashboard pelo menu, o título da página e o caminho de navegação mostram "Despesas Fixas". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Clicar em "Dashboard" no menu lateral (rota `/dash`). |
| 3. Olhar o título da página e o caminho de navegação no topo. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O título e o caminho de navegação devem mostrar "Dashboard". | O topo mostra "Início > Despesas Fixas" e o título "Despesas Fixas", enquanto o conteúdo é o do Dashboard. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Dashboard / Título da página | C03-CT01: Abrir a página Dashboard. |

| **Evidência(s)** |
|---|
| [BUG:12] [PENDENTE BUGS] (roteiro V01) |

---

### 🐞 **Bug 13: Títulos dos gráficos do Dashboard ficam ilegíveis**

| **ID** | **Descrição** |
|---|---|
| BUG-013 | No Dashboard, os títulos dos blocos de gráficos e dos próprios gráficos quase não aparecem, por causa da cor do texto sobre o fundo. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa, com o tema Claro. |
| 2. Abrir o Dashboard (`/dash`). |
| 3. Rolar a página olhando os blocos Clientes, Matrículas, Contas a Receber, Cancelamentos e Avaliações. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| Os títulos dos blocos e dos gráficos devem ter contraste suficiente para serem lidos. | Os títulos (por exemplo "Clientes", "Matrículas", "Frequência", "Idade", "Sexo") aparecem em cor muito próxima à do fundo e quase não dá para ler. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Dashboard / Gráficos | C03-CT02: Conferir os títulos dos gráficos. |

| **Evidência(s)** |
|---|
| [BUG:13] [PENDENTE BUGS] (roteiro V02) |

---

### 🐞 **Bug 14: Quantidade de alunos em risco diverge entre as telas**

| **ID** | **Descrição** |
|---|---|
| BUG-014 | A quantidade de alunos em risco é diferente na Página Inicial, na Inteligência de Retenção da Página Inicial e no Dashboard. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa e olhar o card "alunos em risco de evasão" da Página Inicial. |
| 2. Na mesma página, olhar os totais de Alto, Médio e Baixo risco de "Inteligência de Retenção". |
| 3. Abrir o Dashboard (`/dash`) e olhar o card "Alunos em risco". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| A mesma quantidade de alunos em risco nas três áreas. | Em 28/10/2026: Página Inicial mostra "1 alunos em risco de evasão"; Inteligência de Retenção mostra 0 alto, 4 médio e 0 baixo; Dashboard mostra "0 Alunos em risco". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial e Dashboard / Alunos em risco | C03-CT03: Conferir os alunos em risco entre as telas. |

| **Evidência(s)** |
|---|
| [BUG:14] [PENDENTE BUGS] (roteiro V03) |

---

### 🐞 **Bug 15: Card de avaliações pendentes mostra 0, mas a lista tem pendentes**

| **ID** | **Descrição** |
|---|---|
| BUG-015 | O card da Página Inicial mostra "0 avaliações pendentes", mas a lista de avaliações filtrada por Pendente mostra 4 avaliações. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa e olhar o card de avaliações pendentes da Página Inicial. |
| 2. Clicar em "Ver detalhes" do card (rota `/avaliacoes?status=pendente`). |
| 3. Contar as linhas da lista com status PENDENTE. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O número do card deve ser igual à quantidade de avaliações pendentes da lista. | O card mostra "0 avaliações pendentes". A lista abre com o filtro Pendente e mostra 4 avaliações PENDENTE (#79, #69, #67 e #52). |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Avaliações pendentes | C02-CT03: Abrir as avaliações pendentes pelo card. |

| **Evidência(s)** |
|---|
| [BUG:15] [PENDENTE BUGS] (roteiro V04) |

---

### 🐞 **Bug 16: Paginação de clientes mostra 3 páginas para 1 resultado**

| **ID** | **Descrição** |
|---|---|
| BUG-016 | Na lista de clientes com o filtro Status "Ativo", a tabela tem 1 cliente, mas a paginação oferece as páginas 1, 2 e 3. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Clientes" (`/clientes`) mantendo o Status "Ativo". |
| 3. Olhar a tabela e a paginação abaixo dela. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| A paginação deve oferecer só as páginas que têm clientes (uma página). | A tabela mostra 1 cliente (408 - Lila) e o card "Clientes Ativos" mostra 1, mas a paginação mostra "Anterior 1 2 3 Próxima". Com Status "Todos", a lista mostra 122 clientes. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Clientes / Paginação | C04-CT01: Listar clientes e conferir a paginação. |

| **Evidência(s)** |
|---|
| [BUG:16] [PENDENTE BUGS] (roteiro V05) |

---

### 🐞 **Bug 17: Campo Código da busca de clientes aceita letras**

| **ID** | **Descrição** |
|---|---|
| BUG-017 | O campo Código da busca de clientes aceita letras, embora o código seja numérico. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Clientes" (`/clientes`). |
| 3. Digitar "abc" no campo Código. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O campo deve aceitar só números. | O campo mantém o texto "abc". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Clientes / Busca por código | C04-CT04: Digitar letras no campo Código. |

| **Evidência(s)** |
|---|
| [BUG:17] [PENDENTE BUGS] (roteiro V07) |

---

### 🐞 **Bug 18: Matrículas ativas pertencem a clientes inativos**

| **ID** | **Descrição** |
|---|---|
| BUG-018 | A tela de Matrículas mostra 3 matrículas ativas, mas a tela de Clientes mostra só 1 cliente ativo. Os clientes das outras duas matrículas ativas aparecem como INATIVO. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Matrículas" (`/matriculas`) e anotar as matrículas com status ATIVO. |
| 3. Abrir "Clientes" (`/clientes`) com Status "Ativo" e depois com "Todos". |
| 4. Procurar os nomes das matrículas ativas. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| Cada matrícula ativa deve pertencer a um cliente ativo, e a quantidade de clientes ativos deve ser coerente com as matrículas ativas. | Matrículas ativas: 242 (Marcelo Longo Zandonadi), 241 (Rafaela Andrade) e 240 (Lila). Clientes ativos: apenas 408 (Lila). Os cadastros de Marcelo Longo Zandonadi e Rafaela Andrade aparecem como INATIVO. A Página Inicial também mostra 1 cliente ativo. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Matrículas / Clientes | C05-CT03: Conferir matrículas ativas com os clientes ativos. |

| **Evidência(s)** |
|---|
| [BUG:18] [PENDENTE BUGS] (roteiro V10) |

---

### 🐞 **Bug 19: Totais de Contas a Receber não fecham com a listagem**

| **ID** | **Descrição** |
|---|---|
| BUG-019 | No período do mês, "Entradas" mostra R$ 499,50 (soma das linhas), mas "Recebido no Mês" mostra R$ 475,00 com "100,00% recebido". A conta 1608 tem valor recebido maior que o valor a receber. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Contas a Receber" (`/contas-receber`) com o período do mês. |
| 3. Somar a coluna "Valor recebido" das linhas. |
| 4. Comparar com "Entradas", "Previsto para o Mês" e "Recebido no Mês". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| Os totais devem bater com as linhas, e um valor recebido acima do valor a receber deve ser explicado ou impedido. | As seis linhas somam R$ 499,50 (igual a "Entradas"). "Previsto para o Mês" e "Recebido no Mês" mostram R$ 475,00. A conta 1608 (Lila, Matrícula) tem R$ 75,50 a receber e R$ 100,00 recebido. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Contas a Receber / Totais | C06-CT01: Conferir os totais com a listagem. |

| **Evidência(s)** |
|---|
| [BUG:19] [PENDENTE BUGS] (roteiro V11) |

---

### 🐞 **Bug 20: Erro 500 ao salvar conta a pagar com campos vazios**

| **ID** | **Descrição** |
|---|---|
| BUG-020 | Ao salvar uma nova conta a pagar sem preencher nada, a requisição retorna 500 e a tela mostra apenas "Erro ao salvar conta a pagar". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Contas a Pagar" (`/contas-pagar`). |
| 3. Clicar em "Nova Conta". |
| 4. Sem preencher nada, clicar em salvar. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar quais campos obrigatórios faltam, sem erro de servidor. | `POST /api/cadastrar-conta-pagar/1` retorna 500 e a tela mostra "Erro ao salvar conta a pagar", sem dizer o que falta. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Contas a Pagar / Nova conta | C07-CT01: Criar conta a pagar com campos vazios. |

| **Evidência(s)** |
|---|
| [BUG:20] [PENDENTE BUGS] (roteiro V12) |

---

### 🐞 **Bug 21: Erro 500 ao abrir caixa com campos vazios**

| **ID** | **Descrição** |
|---|---|
| BUG-021 | Ao tentar abrir um caixa sem preencher nada, a requisição retorna 500 e a tela mostra "Erro no servidor. Erro interno inesperado.". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Caixas" (`/caixas`). |
| 3. Clicar em "Abrir Caixa". |
| 4. Sem preencher nada, confirmar a abertura. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar quais campos faltam, sem erro de servidor. | `POST /api/abrir-caixa/1` retorna 500 e a tela mostra "Erro no servidor. Erro interno inesperado.". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Caixas / Abrir caixa | C08-CT01: Abrir caixa com campos vazios. |

| **Evidência(s)** |
|---|
| [BUG:21] [PENDENTE BUGS] (roteiro V13) |

---

### 🐞 **Bug 22: Check-ins do dia não batem com a lista de check-ins**

| **ID** | **Descrição** |
|---|---|
| BUG-022 | O card "Check-ins hoje" mostra 3 e "18% vs ontem", mas a tabela está vazia, "Presentes agora" é 0 e a meta do dia está em 0%. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Check-in" (`/checkin`). |
| 3. Olhar o card "Check-ins hoje", "Meta do dia" e a tabela de check-ins. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| A quantidade de check-ins do dia deve ser a mesma nos indicadores e na tabela, e a meta deve considerar esses check-ins. | Em 28/10/2026: "3 Check-ins hoje", "18% vs ontem", "Presentes agora 0", "0% da meta" (meta 100) e a tabela mostra "Nenhum registro encontrado". Em "Presenças" também aparece "Nenhuma presença encontrada". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Check-in / Indicadores | C09-CT01: Conferir os indicadores do Check-in com a lista. |

| **Evidência(s)** |
|---|
| [BUG:22] [PENDENTE BUGS] (roteiro V14) |

---

### 🐞 **Bug 23: Horário de pico diferente entre Página Inicial e Check-in**

| **ID** | **Descrição** |
|---|---|
| BUG-023 | A Página Inicial mostra o pico de movimento em "00h - 01h", e a tela de Check-in mostra "18h às 20h". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa e olhar o card "Pico de movimento" da Página Inicial. |
| 2. Abrir "Check-in" (`/checkin`) e olhar "Pico de movimento". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O horário de pico deve ser o mesmo nas duas telas. | Página Inicial: "00h - 01h". Check-in: "Horário de maior movimento: 18h às 20h". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Check-in / Pico de movimento | C09-CT02: Conferir o horário de pico entre as telas. |

| **Evidência(s)** |
|---|
| [BUG:23] [PENDENTE BUGS] (roteiro V15) |

---

### 🐞 **Bug 24: Erro 500 ao salvar colaborador com campos vazios**

| **ID** | **Descrição** |
|---|---|
| BUG-024 | Ao salvar um novo colaborador sem preencher nada, a requisição retorna 500 e a tela mostra "Erro no servidor. Erro interno inesperado.". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Colaboradores" (`/colaboradores`). |
| 3. Clicar em "Novo Colaborador". |
| 4. Sem preencher nada, clicar em "Salvar". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar quais campos obrigatórios faltam, sem erro de servidor. | `POST /api/salvar/colaborador/1` retorna 500 e a tela mostra "Erro no servidor. Erro interno inesperado.". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Colaboradores / Cadastro | C11-CT01: Cadastrar colaborador com campos vazios. |

| **Evidência(s)** |
|---|
| [BUG:24] [PENDENTE BUGS] (roteiro V17) |

---

### 🐞 **Bug 25: Cadastro de Planos não avisa nada ao salvar vazio**

| **ID** | **Descrição** |
|---|---|
| BUG-025 | Ao clicar em "Salvar Plano" com o formulário vazio, o sistema não mostra mensagem e nenhuma requisição é enviada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Planos" (`/planos`). |
| 3. Clicar em "Novo Plano". |
| 4. Sem preencher nada, clicar em "Salvar Plano". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta. | Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. A pessoa não sabe por que o cadastro não foi salvo. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Planos / Cadastro | C12-CT01: Salvar Planos com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:25] [PENDENTE BUGS] (roteiro V19) |

---

### 🐞 **Bug 26: Cadastro de Prospecção não avisa nada ao salvar vazio**

| **ID** | **Descrição** |
|---|---|
| BUG-026 | Ao clicar em "Salvar Lead" com o formulário vazio, o sistema não mostra mensagem e nenhuma requisição é enviada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Prospecção" (`/prospeccao`). |
| 3. Clicar em "Adicionar Lead". |
| 4. Sem preencher nada, clicar em "Salvar Lead". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta. | Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. A pessoa não sabe por que o cadastro não foi salvo. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Prospecção / Cadastro | C12-CT04: Salvar Prospecção com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:26] [PENDENTE BUGS] (roteiro V20) |

---

### 🐞 **Bug 27: Cadastro de Funções não avisa nada ao salvar vazio**

| **ID** | **Descrição** |
|---|---|
| BUG-027 | Ao clicar em "Salvar Função" com o formulário vazio, o sistema não mostra mensagem e nenhuma requisição é enviada. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Funções" (`/funcoes`). |
| 3. Clicar em "Nova Função". |
| 4. Sem preencher nada, clicar em "Salvar Função". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta. | Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. A pessoa não sabe por que o cadastro não foi salvo. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Funções / Cadastro | C12-CT05: Salvar Funções com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:27] [PENDENTE BUGS] (roteiro V21) |

---

### 🐞 **Bug 28: Erro genérico ao salvar produto vazio**

| **ID** | **Descrição** |
|---|---|
| BUG-028 | Ao salvar um produto vazio, a requisição retorna 400 e a tela mostra só "Erro ao salvar produto", sem indicar o campo que falta. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Produtos" (`/produtos`). |
| 3. Clicar em "Novo". |
| 4. Sem preencher nada, clicar em "Salvar". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta. | `POST /api/criar-produto/1` retorna 400 e a tela mostra "Erro ao salvar produto". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Produtos / Cadastro | C12-CT06: Salvar Produtos com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:28] [PENDENTE BUGS] (roteiro V22) |

---

### 🐞 **Bug 29: Erro genérico ao salvar enquete vazia**

| **ID** | **Descrição** |
|---|---|
| BUG-029 | Ao salvar uma enquete vazia, a requisição retorna 200, mas a tela mostra "Erro ao salvar enquete", sem indicar o que falta. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Baixa | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Enquetes" (`/enquetes`). |
| 3. Clicar em "Nova Enquete". |
| 4. Sem preencher nada, clicar em "Salvar". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta. | `POST /api/enquete/salvar/1` retorna 200 e a tela mostra "Erro ao salvar enquete". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Enquetes / Cadastro | C12-CT09: Salvar Enquetes com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:29] [PENDENTE BUGS] (roteiro V23) |

---

### 🐞 **Bug 30: Atividades permite salvar registro em branco**

| **ID** | **Descrição** |
|---|---|
| BUG-030 | Ao salvar o formulário de Atividades vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Atividades" (`/atividades`). |
| 3. Clicar em "Nova Atividade". |
| 4. Sem preencher nada, clicar em "Salvar". |
| 5. Olhar a lista. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve exigir o nome e não criar o registro. | `POST /api/salvar-atividade/1` retorna 201 e a lista passa de 4 para 5 registros, com a linha 5 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Atividades / Cadastro | C12-CT10: Salvar Atividades com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:30] [PENDENTE BUGS] (roteiro V24) |

---

### 🐞 **Bug 31: Objetivos de Treino permite salvar registro em branco**

| **ID** | **Descrição** |
|---|---|
| BUG-031 | Ao salvar o formulário de Objetivos de Treino vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Objetivos de Treino" (`/objetivos-treino`). |
| 3. Clicar em "Novo Objetivo". |
| 4. Sem preencher nada, clicar em "Salvar". |
| 5. Olhar a lista. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve exigir o nome e não criar o registro. | `POST /api/objetivo-treino/salvar/1` retorna 201 e a lista passa de 0 para 1 registros, com a linha 1 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Objetivos de Treino / Cadastro | C12-CT14: Salvar Objetivos de Treino com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:31] [PENDENTE BUGS] (roteiro V25) |

---

### 🐞 **Bug 32: Tipos de Pagamento permite salvar registro em branco**

| **ID** | **Descrição** |
|---|---|
| BUG-032 | Ao salvar o formulário de Tipos de Pagamento vazio, o sistema aceita e cria um registro sem nome. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Tipos de Pagamento" (`/tipos-pagamento`). |
| 3. Clicar em "Novo". |
| 4. Sem preencher nada, clicar em "Salvar". |
| 5. Olhar a lista. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve exigir o nome e não criar o registro. | `POST /api/cria/tipo-pagamento/1` retorna 201 e a lista passa de 10 para 11 registros, com a linha 12 sem nome. Nenhuma mensagem de validação aparece. |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Tipos de Pagamento / Cadastro | C12-CT15: Salvar Tipos de Pagamento com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:32] [PENDENTE BUGS] (roteiro V26) |

---

### 🐞 **Bug 33: Erro 500 ao salvar pergunta de anamnese vazia**

| **ID** | **Descrição** |
|---|---|
| BUG-033 | Ao salvar uma pergunta de anamnese vazia, a requisição retorna 500 e a tela mostra "Erro ao salvar pergunta". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar no Sifit Unialfa. |
| 2. Abrir "Perguntas" de Anamnese (`/perguntas-anamnese`). |
| 3. Clicar em "Nova Pergunta". |
| 4. Sem preencher nada, clicar em "Salvar". |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve informar o campo obrigatório que falta, sem erro de servidor. | `POST /api/pergunta-anamnese/salvar/1` retorna 500 e a tela mostra "Erro ao salvar pergunta". |

| **Ambiente** |
|---|
| Sifit Unialfa |
| https://sifitalfa.centrion.com.br/ |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| 28/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Perguntas de Anamnese / Cadastro | C12-CT16: Salvar Perguntas de Anamnese com o formulário vazio. |

| **Evidência(s)** |
|---|
| [BUG:33] [PENDENTE BUGS] (roteiro V27) |

---
