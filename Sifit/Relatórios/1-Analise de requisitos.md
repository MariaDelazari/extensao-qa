# Análise de Requisitos

### 🔐 RF01 - Login com Credenciais Válidas

**Cenário de teste:** C01 (`CT_RF01_`)

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

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve impedir a autenticação quando o usuário informar credenciais inválidas.

**Funcionalidades esperadas:**

- Verificar se o nome de usuário e a senha correspondem a uma conta válida.
- Impedir o acesso ao sistema quando as credenciais forem incorretas.
- Exibir uma mensagem clara informando que as credenciais são inválidas.
- Tratar falhas de autenticação sem apresentar erros internos do servidor ao usuário.

**Resultado esperado:** O sistema deve negar o acesso quando as credenciais forem inválidas, permanecer na tela de login e apresentar uma mensagem informativa, sem gerar um erro interno do servidor.

---

### 🔐 RF03 - Validação dos Campos Obrigatórios no Login

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve exigir o preenchimento dos campos de nome de usuário e senha antes de realizar a autenticação.

**Funcionalidades esperadas:**

- Identificar quando o campo de nome de usuário estiver vazio.
- Identificar quando o campo de senha estiver vazio.
- Impedir o envio da requisição de login enquanto houver campos obrigatórios não preenchidos.
- Informar ao usuário quais campos precisam ser preenchidos.

**Resultado esperado:** O sistema deve impedir a tentativa de login com os campos obrigatórios vazios e apresentar mensagens claras na interface, orientando o usuário a preencher os dados necessários.

---

### 🔐 RF04 - Tratamento de Espaços Extras nas Credenciais

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve tratar adequadamente os espaços extras inseridos no início ou no final dos campos de credenciais, conforme as regras de autenticação definidas para a aplicação.

**Funcionalidades esperadas:**

- Verificar como os espaços extras são tratados nos campos de nome de usuário e senha.
- Aplicar o tratamento definido para cada campo durante a validação das credenciais.
- Evitar que espaços acidentais provoquem falhas de autenticação quando os dados deveriam ser considerados válidos.

**Resultado esperado:** O sistema deve processar as credenciais de acordo com as regras definidas para cada campo, permitindo a autenticação quando os dados forem válidos segundo essas regras.

---

### 🔐 RF05 - Recuperação de Senha

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve disponibilizar uma funcionalidade que permita ao usuário iniciar o processo de recuperação de senha pela tela de login.

**Funcionalidades esperadas:**

- Disponibilizar o link "Esqueci minha senha" na tela de login.
- Permitir que o usuário acesse a funcionalidade de recuperação de senha pelo link correspondente.
- Direcionar o usuário para a página ou etapa de recuperação de senha.

**Resultado esperado:** Ao clicar em "Esqueci minha senha", o sistema deve direcionar o usuário para o fluxo de recuperação de senha.

---

### 🔐 RF06 - Persistência da Sessão de Login

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve permitir que o usuário mantenha sua autenticação ao retornar à aplicação quando a opção "Manter conectado" estiver selecionada, conforme o comportamento previsto para essa funcionalidade.

**Funcionalidades esperadas:**

- Disponibilizar a opção "Manter conectado" na tela de login.
- Considerar a opção selecionada durante o processo de autenticação.
- Manter a autenticação do usuário ao retornar à aplicação, conforme as regras de persistência da sessão.
- Solicitar uma nova autenticação quando não houver uma sessão válida, de acordo com as regras definidas para o sistema.

**Resultado esperado:** Quando a opção "Manter conectado" estiver selecionada, o sistema deve preservar a autenticação conforme o comportamento previsto. Caso não exista uma sessão válida, o usuário deve ser direcionado à tela de login.

---

### 🔐 RF07 - Controle de Acesso às Áreas Autenticadas

**Cenário de teste:** C01 (`CT_RF01_`)

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

**Cenário de teste:** C02 (`CT_RF02_`)

**Descrição:** Depois do login, o sistema deve exibir a página inicial com o resumo da academia, com saudação, data e indicadores que levam ao detalhe de cada informação.

**Funcionalidades esperadas:**

- Exibir a saudação com o nome da conta autenticada e a data de hoje.
- Exibir o texto "Aqui está o resumo da sua academia hoje".
- Exibir os cards de alunos em risco de evasão, valor em aberto, pico de movimento e avaliações pendentes, cada um com o link "Ver detalhes".
- Exibir os cards Clientes Ativos, Clientes Ausentes, Sem Matrículas, Personais, Matrículas no Período, Desistências no Período e Renovações.
- Abrir o detalhe de cada card, com valores iguais aos do card.

**Resultado esperado:** A página inicial abre em `/dashboard` com o nome de quem entrou, e os valores dos cards conferem com as telas de detalhe.

---

### 📊 RF09 - Dashboard

**Cenário de teste:** C03 (`CT_RF03_`)

**Descrição:** O sistema deve exibir a página Dashboard com os gráficos de clientes, matrículas, contas a receber, cancelamentos e avaliações, e os indicadores da Inteligência Sifit.

**Funcionalidades esperadas:**

- Abrir o Dashboard pelo menu lateral, na rota `/dash`.
- Exibir o título e o caminho de navegação do Dashboard.
- Exibir os indicadores da Inteligência Sifit: alunos em risco, aniversariantes, avaliações vencendo e frequência em queda.
- Exibir os gráficos de Clientes (frequência, idade, sexo), Matrículas (por mês, por plano), Contas a Receber, Cancelamentos e Avaliações.
- Manter os indicadores coerentes com a Página Inicial.

**Resultado esperado:** O Dashboard abre com o título correto, com gráficos legíveis e indicadores iguais aos das demais telas.

---

### 👥 RF10 - Gestão de clientes

**Cenário de teste:** C04 (`CT_RF04_`)

**Descrição:** O sistema deve permitir listar, buscar, filtrar e cadastrar clientes, validando os campos obrigatórios.

**Funcionalidades esperadas:**

- Listar os clientes com filtros de Código, Nome, Status, Situação, Plano e Personal.
- Exibir os indicadores Clientes Cadastrados, Clientes Ativos, Sem Matrículas e Ausentes.
- Buscar por parte do nome e pelo código.
- Paginar a lista de acordo com o resultado do filtro.
- Cadastrar cliente em `/adicionar-cliente`, exigindo Nome, Status, Sexo e Data de Nascimento.

**Resultado esperado:** A lista, a busca e a paginação refletem o filtro aplicado, e o cadastro não segue com os obrigatórios vazios.

---

### 📝 RF11 - Gestão de matrículas

**Cenário de teste:** C05 (`CT_RF05_`)

**Descrição:** O sistema deve permitir listar e cadastrar matrículas vinculadas a clientes.

**Funcionalidades esperadas:**

- Listar matrículas com código, nome, plano e status, e os indicadores Matrículas Ativas, Recorrentes, Não Renovadas e Cadastradas este Mês.
- Cadastrar matrícula em `/adicionar-matricula`, exigindo a seleção do cliente.
- Manter as matrículas ativas coerentes com os clientes ativos.

**Resultado esperado:** A matrícula só é salva com cliente selecionado e as matrículas ativas pertencem a clientes ativos.

---

### 💰 RF12 - Contas a receber

**Cenário de teste:** C06 (`CT_RF06_`)

**Descrição:** O sistema deve listar as contas a receber do período e apresentar os totais financeiros.

**Funcionalidades esperadas:**

- Filtrar por tipo de data, período e status.
- Exibir Entradas, Saídas, Líquido, Previsto para o Mês, Recebido no Mês, Pendentes e Atrasadas.
- Exibir cliente, título, valor a receber, valor recebido e status de cada conta.

**Resultado esperado:** Os totais conferem com as contas listadas.

---

### 💸 RF13 - Contas a pagar

**Cenário de teste:** C07 (`CT_RF07_`)

**Descrição:** O sistema deve permitir cadastrar e listar contas a pagar.

**Funcionalidades esperadas:**

- Filtrar por tipo de data, período e status.
- Cadastrar nova conta pela ação "Nova Conta".
- Informar ao usuário os campos obrigatórios que faltarem.

**Resultado esperado:** A conta só é salva com os dados exigidos e o sistema orienta o que falta, sem erro interno.

---

### 🏧 RF14 - Caixas

**Cenário de teste:** C08 (`CT_RF08_`)

**Descrição:** O sistema deve permitir listar e abrir caixas.

**Funcionalidades esperadas:**

- Listar caixas por período e status (Aberto ou Fechado).
- Exibir Caixas Abertos, Caixas Fechados, Locais de Caixa e Registros no Período.
- Abrir caixa pela ação "Abrir Caixa", informando o que faltar.

**Resultado esperado:** O caixa só é aberto com os dados exigidos e o sistema orienta o que falta, sem erro interno.

---

### 📍 RF15 - Check-in e presenças

**Cenário de teste:** C09 (`CT_RF09_`)

**Descrição:** O sistema deve exibir os check-ins do dia e as presenças dos clientes.

**Funcionalidades esperadas:**

- Exibir Check-ins hoje, Presentes agora, Meta do dia, Média diária e Taxa de frequência.
- Listar os check-ins do dia com cliente, plano, horário, entrada, saída, unidade e status.
- Exibir o pico de movimento.
- Listar presenças por período em `/presencas`.

**Resultado esperado:** Os indicadores do Check-in batem com a lista e com as demais telas.

---

### 📏 RF16 - Avaliações físicas

**Cenário de teste:** C10 (`CT_RF10_`)

**Descrição:** O sistema deve permitir listar, filtrar e cadastrar avaliações físicas.

**Funcionalidades esperadas:**

- Listar avaliações com filtros de Código, Nome e Status (Pendente ou Realizado).
- Cadastrar avaliação, exigindo a seleção do aluno.

**Resultado esperado:** A avaliação só é salva com aluno selecionado.

---

### 🧑‍🏫 RF17 - Colaboradores

**Cenário de teste:** C11 (`CT_RF11_`)

**Descrição:** O sistema deve permitir listar e cadastrar colaboradores.

**Funcionalidades esperadas:**

- Listar colaboradores com os indicadores Colaboradores Cadastrados, Ativos e Personais.
- Cadastrar colaborador em `/adicionar-colaborador`, informando o que faltar.

**Resultado esperado:** O colaborador só é salvo com os dados exigidos e o sistema orienta o que falta, sem erro interno.

---

### 🗂️ RF18 - Cadastros de apoio

**Cenário de teste:** C12 (`CT_RF12_`)

**Descrição:** O sistema deve permitir cadastrar itens de apoio (planos, fornecedores, turmas, prospecção, funções, produtos, bandeiras, pontuação, enquetes, atividades, tipos de documento, exercícios, categorias, objetivos de treino, tipos de pagamento e perguntas de anamnese) exigindo o nome.

**Funcionalidades esperadas:**

- Abrir o formulário pelo botão de novo cadastro de cada tela.
- Impedir o salvamento quando o nome estiver vazio.
- Informar o campo obrigatório que falta.

**Resultado esperado:** Nenhum registro em branco é criado e o campo obrigatório é indicado.
