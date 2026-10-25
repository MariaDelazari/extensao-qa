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

### 🔐 RF04 - Tratamento de Espaços Extras nas Credenciais

**Descrição:** O sistema deve tratar adequadamente os espaços extras inseridos no início ou no final dos campos de credenciais, conforme as regras de autenticação definidas para a aplicação.

**Funcionalidades esperadas:**

- Verificar como os espaços extras são tratados nos campos de nome de usuário e senha.
- Aplicar o tratamento definido para cada campo durante a validação das credenciais.
- Evitar que espaços acidentais provoquem falhas de autenticação quando os dados deveriam ser considerados válidos.

**Resultado esperado:** O sistema deve processar as credenciais de acordo com as regras definidas para cada campo, permitindo a autenticação quando os dados forem válidos segundo essas regras.

---

