# Relatório de Bugs

**Software:** Sifit Centrion

**Versão:** Sifit Centrion e Sifit Unialfa

**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, https://sifitalfa.centrion.com.br/

**QA responsável:** Maria Eduarda Pacheco Delazari

**Data:** 12.10.26. Em 24/10/2026, os testes continuaram no Sifit Unialfa.

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
| Ambiente de testes |
| Desktop Ubuntu 26.04 LTS |
| Google Chrome 150.0.7871.46 |
| https://sifitalfa.centrion.com.br/ |

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
| https://sifitalfa.centrion.com.br/dashboard |
| Linux |
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
| https://sifitalfa.centrion.com.br/dashboard |
| Linux |
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
| https://sifitalfa.centrion.com.br/dashboard |
| Linux |
| Google Chrome 150.0.7871.46 |
| 25/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Mensalidades em aberto | C02-CT02: Conferir os cards do resumo da academia. |

| **Evidência(s)** |
|---|
| [BUG:10](https://jam.dev/c/63ec10f5-e5b6-4150-a1f6-8e0c1978f806) |

---

### 🐞 **Bug 11: Card de avaliações pendentes não confere com a lista**

| **ID** | **Descrição** |
|---|---|
| BUG-011 | Na página inicial do Sifit Unialfa, o card mostra 0 avaliações pendentes. Ao abrir o filtro Pendente, a tela Avaliações lista registros com status PENDENTE, entre eles os códigos 79, 67, 66 e 52. O resumo "Avaliação no Mês" mostra 2. |

| **Severidade** | **Prioridade** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Entrar em https://sifitalfa.centrion.com.br/dashboard. |
| 2. Anotar o número do card de avaliações pendentes. |
| 3. Abrir https://sifitalfa.centrion.com.br/avaliacoes?status=pendente. |
| 4. Comparar o card, o resumo "Avaliação no Mês" e as linhas com status PENDENTE. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O card deve mostrar a mesma quantidade de avaliações pendentes que a lista filtrada. | O card mostra 0. A lista filtrada exibe avaliações PENDENTE, e o resumo do mês mostra 2. |

| **Ambiente** |
|---|
| https://sifitalfa.centrion.com.br/avaliacoes?status=pendente |
| Linux |
| Google Chrome 150.0.7871.46 |
| 25/10/2026 |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Página inicial / Avaliações | C02-CT03: Abrir as avaliações pendentes pelo card. |

| **Evidência(s)** |
|---|
| [BUG:11](https://jam.dev/c/4f672eb2-1483-4e93-8181-cea811350409) |


---

### 🐞 **Bug 12: O campo de senha não deixa ver o que foi digitado**

| **ID** | **Descrição** |
|---|---|
| BUG-012 | Na tela de login, o campo de senha não tem ícone nem outra opção para mostrar os caracteres. A pessoa não consegue conferir a senha antes de clicar em Entrar. |

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
| [BUG:12](https://jam.dev/c/1c6d4e56-7c8b-43d3-9134-c3bde64d0d80) |
