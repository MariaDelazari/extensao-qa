# Análise de Requisitos

### 🔐 RF01 - Login com Credenciais Válidas

**Descrição:** O sistema deve permitir que o usuário acesse a aplicação utilizando um nome de usuário e uma senha válidos.

**Funcionalidades esperadas:**

- Informar um nome de usuário cadastrado no sistema.
- Informar a senha correspondente à conta.
- Validar as credenciais informadas.
- Permitir o acesso ao sistema quando as credenciais forem válidas.
- Redirecionar o usuário para o dashboard inicial após a autenticação.
- Exibir as funcionalidades e os menus conforme as permissões do usuário autenticado.

**Resultado esperado:** O login deve ser realizado com sucesso, permitindo que o usuário acesse o sistema e visualize o dashboard inicial do Sifit Centrion.

---

### 🔐 RF02 - Validação de Credenciais Inválidas

**Descrição:** O sistema deve impedir a autenticação quando o usuário informar credenciais inválidas.

**Funcionalidades esperadas:**

- Verificar se o nome de usuário e a senha correspondem a uma conta válida.
- Impedir o acesso ao sistema quando as credenciais forem incorretas.
- Exibir uma mensagem clara informando que as credenciais são inválidas.
- Tratar falhas de autenticação sem apresentar erros internos do servidor ao usuário.

**Resultado esperado:** O sistema deve negar o acesso quando as credenciais forem inválidas, permanecer na tela de login e apresentar uma mensagem informativa, sem gerar um erro interno do servidor.

---

### 🔐 RF03 - Validação dos Campos Obrigatórios no Login

**Descrição:** O sistema deve exigir o preenchimento dos campos de nome de usuário e senha antes de realizar a autenticação.

**Funcionalidades esperadas:**

- Identificar quando o campo de nome de usuário estiver vazio.
- Identificar quando o campo de senha estiver vazio.
- Impedir o envio da requisição de login enquanto houver campos obrigatórios não preenchidos.
- Informar ao usuário quais campos precisam ser preenchidos.

**Resultado esperado:** O sistema deve impedir a tentativa de login com os campos obrigatórios vazios e apresentar mensagens claras na interface, orientando o usuário a preencher os dados necessários.

---

