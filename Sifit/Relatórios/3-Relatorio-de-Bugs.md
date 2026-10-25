# Relatório de Bugs

**Software:** Sifit Centrion

**QA responsável:** Maria Eduarda Pacheco Delazari

**Data:** 12.10.26

---

### 🐞 **Bug 01: Falha no login ao inserir espaços extras nas credenciais válidas**

| **ID** | **Descrição** |
|---|---|
| BUG-001 | Ao inserir credenciais válidas com espaços extras no início ou no final dos campos de login, o sistema impede a autenticação, mesmo quando as credenciais são válidas. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a página de login. |
| 2. Inserir um nome de usuário válido com espaços extras no início ou no final. |
| 3. Inserir uma senha válida, adicionando espaços extras conforme o cenário de teste. |
| 4. Clicar no botão verde "Entrar". |
| 5. Verificar se a autenticação é realizada corretamente. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve tratar adequadamente os espaços extras no início e no final dos campos de credenciais, permitindo o login quando os dados informados forem válidos. | O sistema rejeita o login quando há espaços extras nos campos de credenciais e exibe a mensagem "Nome de usuário e senha não correspondem", mesmo com dados válidos, levando o usuário a acreditar que informou as credenciais incorretamente. |

| **Ambiente** |
|---|
| Ambiente de testes. |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46. |
| Sifit Centrion. |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Autenticação | C01-CT01: Login com credenciais válidas contendo espaços extras. |

| **Evidência(s)** |
|---|
| [BUG:01](https://jam.dev/c/51531b19-254b-468b-ad89-7487194fc22a) |

---

### 🐞 **Bug 02: Link "Esqueci minha senha" não funciona**

| **ID** | **Descrição** |
|---|---|
| BUG-002 | Ao clicar no link "Esqueci minha senha" na tela de login, o sistema não realiza nenhum redirecionamento, impedindo o acesso à funcionalidade de recuperação de senha. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a página de login. |
| 2. Localizar o link "Esqueci minha senha". |
| 3. Clicar no link. |
| 4. Verificar se ocorre o redirecionamento para a página de recuperação de senha. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve direcionar o usuário para a página de recuperação de senha ao clicar no link correspondente. | Ao clicar no link, nenhum redirecionamento é realizado, e o usuário permanece na tela de login. |

| **Ambiente** |
|---|
| Ambiente de testes. |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46. |
| Sifit Centrion. |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Recuperação de senha | C01-CT01: Acessar a funcionalidade de recuperação de senha. |

| **Evidência(s)** |
|---|
| [BUG:02](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

---

### 🐞 **Bug 03: Erro interno do servidor ao validar credenciais inválidas no login**

| **ID** | **Descrição** |
|---|---|
| BUG-003 | Ao inserir uma senha incorreta na tela de login, a requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.". A resposta da API contém `"verifica_erro": true`, indicando uma falha, mas não identifica o problema como credenciais inválidas. O sistema deveria tratar a tentativa como uma falha de autenticação e apresentar uma mensagem clara ao usuário. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a página de login. |
| 2. Inserir um nome de usuário válido. |
| 3. Inserir uma senha incorreta. |
| 4. Clicar no botão verde "Entrar". |
| 5. Verificar a resposta da requisição `POST /api/login` na aba Network das ferramentas de desenvolvedor do navegador. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve validar as credenciais informadas e, caso sejam inválidas, retornar uma resposta apropriada de falha de autenticação, como "Nome de usuário ou senha inválidos", sem gerar um erro interno do servidor. | A requisição `POST /api/login` retorna o status `500 Internal Server Error`, e a interface exibe a mensagem "Erro no servidor. Erro interno inesperado.", em vez de informar que as credenciais estão incorretas. |

| **Ambiente** |
|---|
| Ambiente de testes. |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46. |
| Sifit Centrion. |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Autenticação | C01-CT02: Login com credenciais inválidas. |

| **Evidência(s)** |
|---|
| [BUG:03](https://jam.dev/c/a6cbb545-f415-4e44-b446-20f146f32a1c) |


---



### 🐞 **Bug 04: Ausência de validação de campos obrigatórios no login**

| **ID** | **Descrição** |
|---|---|
| BUG-004 | Ao tentar realizar o login com os campos de nome de usuário e senha vazios, o sistema permite o envio da requisição à API sem validar previamente os campos obrigatórios. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
|---|---|---|
| Média | Alta | Aberto |

| **Passo a passo para simular o bug** |
|---|
| 1. Acessar a página de login. |
| 2. Manter os campos de nome de usuário e senha vazios. |
| 3. Clicar no botão verde "Entrar". |
| 4. Verificar a resposta da API e as mensagens exibidas na interface e no console do navegador. |

| **Comportamento Esperado** | **Comportamento Obtido** |
|---|---|
| O sistema deve validar os campos obrigatórios antes de enviar a requisição, informando ao usuário que o nome de usuário e a senha devem ser preenchidos. | O sistema envia a requisição à API mesmo com os campos vazios. A API retorna uma resposta vazia (`[]`), e a mensagem padrão de credenciais inválidas aparece no console do navegador. A interface não informa que os campos são obrigatórios, e o usuário permanece na tela de login. |

| **Ambiente** |
|---|
| Ambiente de testes. |
| Desktop com Ubuntu 26.04 LTS. |
| Google Chrome 150.0.7871.46. |
| Sifit Centrion. |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
|---|---|
| Login / Validação de campos obrigatórios | C01-CT03: Tentativa de login com campos obrigatórios vazios. |

| **Evidência(s)** |
|---|
| [BUG:04](https://jam.dev/c/fcd3f7a9-9e1b-4aa3-a683-f5155d753e53) |

---

