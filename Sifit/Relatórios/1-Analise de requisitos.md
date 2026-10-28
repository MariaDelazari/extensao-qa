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

### 🔐 RF05 - Recuperação de Senha

**Descrição:** O sistema deve disponibilizar uma funcionalidade que permita ao usuário iniciar o processo de recuperação de senha pela tela de login.

**Funcionalidades esperadas:**

- Disponibilizar o link "Esqueci minha senha" na tela de login.
- Permitir que o usuário acesse a funcionalidade de recuperação de senha pelo link correspondente.
- Direcionar o usuário para a página ou etapa de recuperação de senha.

**Resultado esperado:** Ao clicar em "Esqueci minha senha", o sistema deve direcionar o usuário para o fluxo de recuperação de senha.

---

### 🔐 RF06 - Persistência da Sessão de Login

**Descrição:** O sistema deve permitir que o usuário mantenha sua autenticação ao retornar à aplicação quando a opção "Manter conectado" estiver selecionada, conforme o comportamento previsto para essa funcionalidade.

**Funcionalidades esperadas:**

- Disponibilizar a opção "Manter conectado" na tela de login.
- Considerar a opção selecionada durante o processo de autenticação.
- Manter a autenticação do usuário ao retornar à aplicação, conforme as regras de persistência da sessão.
- Solicitar uma nova autenticação quando não houver uma sessão válida, de acordo com as regras definidas para o sistema.

**Resultado esperado:** Quando a opção "Manter conectado" estiver selecionada, o sistema deve preservar a autenticação conforme o comportamento previsto. Caso não exista uma sessão válida, o usuário deve ser direcionado à tela de login.

---

### 🔐 RF07 - Controle de Acesso às Áreas Autenticadas

**Descrição:** O sistema deve permitir o acesso ao dashboard somente quando o usuário possuir uma sessão válida e estiver autenticado.

**Funcionalidades esperadas:**

- Validar a autenticação do usuário ao acessar áreas restritas.
- Verificar a validade da sessão antes de permitir o acesso ao dashboard.
- Impedir o acesso a áreas autenticadas quando o usuário não possuir uma sessão válida.
- Aplicar a validação de acesso mesmo quando o usuário inserir diretamente a URL `/dashboard` na barra de endereços do navegador.
- Redirecionar usuários não autenticados à tela de login.

**Resultado esperado:** O sistema deve permitir o acesso ao dashboard somente para usuários autenticados com uma sessão válida, independentemente de acessarem a área pela navegação da interface ou diretamente pela URL.

---

---

### 🏠 RF08 - Página Inicial do Dashboard

**Descrição:** Depois do login, o sistema deve exibir a página inicial com o resumo da academia, com saudação, data e indicadores que levam ao detalhe de cada informação.

**Funcionalidades esperadas:**

- Exibir a saudação com o nome da conta autenticada e a data de hoje.
- Exibir o texto "Aqui está o resumo da sua academia hoje".
- Exibir os cards de alunos em risco de evasão, valor em aberto, pico de movimento e avaliações pendentes, cada um com o link "Ver detalhes".
- Exibir os cards Clientes Ativos, Clientes Ausentes, Sem Matrículas, Personais, Matrículas no Período, Desistências no Período e Renovações.
- Abrir o detalhe de cada card, com valores iguais aos do card.

**Resultado esperado:** A página inicial abre em `/dashboard` com o nome de quem entrou, e os valores dos cards conferem com as telas de detalhe.
