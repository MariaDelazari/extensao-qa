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