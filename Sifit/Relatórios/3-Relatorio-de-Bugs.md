# Relatório de Bugs

**Software:** Sifit Centrion

**QA responsável:**  Maria Eduarda Pacheco Delazari

**Data:** 22.10.26

---

### 🐞 **Bug 01: Link "Esqueci minha senha" não funciona**

| **ID**  | **Descrição**                                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BUG-001 | Ao clicar no link "Esqueci minha senha" na tela de login, o sistema não realiza nenhum redirecionamento, impedindo o acesso à funcionalidade de recuperação de senha. |

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

|**Ambiente**|
|---|
|Navegador Google Chrome.|
|Aplicação web.|
|Tela de login.|

| **Funcionalidade Afetada**   | **Caso de Teste Relacionado**                              |
| ---------------------------- | ---------------------------------------------------------- |
| Login / Recuperação de senha | C01-CT01: Acessar a funcionalidade de recuperação de senha |

| **Evidência(s)**                                                 |
| ---------------------------------------------------------------- |
| [BUG:01](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

---
