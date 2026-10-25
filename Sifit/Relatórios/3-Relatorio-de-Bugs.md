# Relatório de Bugs

**Software:** Sifit Centrion

**QA responsável:**  Maria Eduarda Pacheco Delazari

**Data:** 12.10.26

---

###  ✅🐞 **Bug 01: Falha no login ao inserir espaços extras nas credenciais válidas**

| **ID**  | **Descrição**                                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-001 | Ao inserir credenciais válidas com espaços extras no início ou no final dos campos de login, o sistema pode impedir a autenticação, mesmo que os dados estejam corretos. |

|**Severidade do Bug**|**Prioridade de Correção**|**Status**|
|---|---|---|
|Média|Média|Aberto|

| **Passo a passo para simular o bug**                                                           |
| ---------------------------------------------------------------------------------------------- |
| 1. Acessar a página de login.                                                                  |
| 2. Inserir um nome de usuário válido com espaços extras no início ou no final.                 |
| 3. Inserir a senha válida, adicionando espaços extras no início ou no final, conforme o teste. |
| 4. Clicar no botão verde "Entrar".                                                             |
| 5. Verificar se a autenticação é realizada corretamente.                                       |

|**Comportamento Esperado**|**Comportamento Obtido**|
|---|---|
|O sistema deve tratar os espaços extras no início e no final dos campos de credenciais adequadamente, permitindo o login quando os dados informados forem válidos.|O sistema pode rejeitar as credenciais e impedir o login quando são inseridos espaços extras nos campos, mesmo que os dados estejam corretos.|

| **Ambiente**                |
| --------------------------- |
| Ambiente de testes.         |
| Desktop Ubuntu 26.04 LTS.   |
| Google Chrome 150.0.7871.46 |
| Sifit Centrion              |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado**                                     |
| -------------------------- | ----------------------------------------------------------------- |
| Login / Autenticação       | C01-CT01:  login com credenciais válidas contendo espaços extras. |

| **Evidência(s)**                                                 |
| ---------------------------------------------------------------- |
| [BUG:01](https://jam.dev/c/51531b19-254b-468b-ad89-7487194fc22a) |

---


---
### ✅ 🐞 **Bug 02: Link "Esqueci minha senha" não funciona** 

| **ID**  | **Descrição**                                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-002 | Ao clicar no link "Esqueci minha senha" na tela de login, o sistema não realiza nenhum redirecionamento, impedindo o acesso à funcionalidade de recuperação de senha. |

|**Severidade do Bug**|**Prioridade de Correção**|**Status**|
|---|---|---|
|Média|Alta|Aberto|

| **Passo a passo para simular o bug**          |
| --------------------------------------------- |
| 1. Acessar a página de login                  |
| 2. Localizar o link "Esqueci minha senha"     |
| 3. Clicar no link                             |
| 4. Verificar se ocorre algum redirecionamento |

| **Comportamento Esperado**                                                 | **Comportamento Obtido**                                                                       |
| -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| O sistema deve direcionar o usuário para a página de recuperação de senha. | Ao clicar no link, nenhum redirecionamento é realizado e o usuário permanece na tela de login. |

| **Ambiente**                |
| --------------------------- |
| Ambiente de testes.         |
| Desktop Ubuntu 26.04 LTS.   |
| Google Chrome 150.0.7871.46 |
| Sifit Centrion              |

| **Funcionalidade Afetada**   | **Caso de Teste Relacionado**                              |
| ---------------------------- | ---------------------------------------------------------- |
| Login / Recuperação de senha | C01-CT01: Acessar a funcionalidade de recuperação de senha |

| **Evidência(s)**                                                 |
| ---------------------------------------------------------------- |
| [BUG:02](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |
