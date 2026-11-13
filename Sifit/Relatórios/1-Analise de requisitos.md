# Análise de Requisitos

Cada requisito tem o mesmo número do cenário e do arquivo de casos: o RF01 é testado no cenário C01 (`CT_RF01_`), o RF02 no C02 (`CT_RF02_`), e assim por diante. Ficaram só os pontos que deram para ver na tela.

---

### 🔐 RF01 - Login na plataforma

**Cenário de teste:** C01 (`CT_RF01_`)

**Descrição:** O sistema deve controlar o acesso por nome de usuário e senha, tratar credenciais inválidas e campos vazios, oferecer recuperação de senha e "Manter conectado" e proteger as áreas internas.

#### Login com credenciais válidas

**Descrição:** O sistema deve permitir que o usuário acesse a aplicação utilizando um nome de usuário e uma senha válidos.

**Funcionalidades esperadas:**

- Informar um nome de usuário cadastrado no sistema.
- Informar a senha correspondente à conta.
- Validar as credenciais informadas.
- Permitir o acesso ao sistema quando as credenciais forem válidas.
- Redirecionar o usuário para o dashboard inicial após a autenticação.
- Exibir as funcionalidades e os menus conforme as permissões do usuário autenticado.

**Resultado esperado:** O login deve ser realizado com sucesso, permitindo que o usuário acesse o sistema e visualize o dashboard inicial do Sifit Centrion.

#### Validação de credenciais inválidas

**Descrição:** O sistema deve impedir a autenticação quando o usuário informar credenciais inválidas, seja senha incorreta ou usuário inexistente.

**Funcionalidades esperadas:**

- Verificar se o nome de usuário e a senha correspondem a uma conta válida.
- Impedir o acesso ao sistema quando as credenciais forem incorretas.
- Exibir uma mensagem clara informando que as credenciais são inválidas.
- Tratar falhas de autenticação sem apresentar erros internos do servidor ao usuário.

**Resultado esperado:** O sistema deve negar o acesso quando as credenciais forem inválidas, permanecer na tela de login e apresentar uma mensagem informativa, sem gerar um erro interno do servidor.

#### Validação dos campos obrigatórios no login

**Descrição:** O sistema deve exigir o preenchimento dos campos de nome de usuário e senha antes de realizar a autenticação.

**Funcionalidades esperadas:**

- Identificar quando o campo de nome de usuário estiver vazio.
- Identificar quando o campo de senha estiver vazio.
- Impedir o envio da requisição de login enquanto houver campos obrigatórios não preenchidos.
- Informar ao usuário quais campos precisam ser preenchidos.

**Resultado esperado:** O sistema deve impedir a tentativa de login com os campos obrigatórios vazios e apresentar mensagens claras na interface, orientando o usuário a preencher os dados necessários.

#### Tratamento de espaços extras nas credenciais

**Descrição:** O sistema deve tratar adequadamente os espaços extras inseridos no início ou no final dos campos de credenciais, conforme as regras de autenticação definidas para a aplicação.

**Funcionalidades esperadas:**

- Verificar como os espaços extras são tratados nos campos de nome de usuário e senha.
- Aplicar o tratamento definido para cada campo durante a validação das credenciais.
- Evitar que espaços acidentais provoquem falhas de autenticação quando os dados deveriam ser considerados válidos.

**Resultado esperado:** O sistema deve processar as credenciais de acordo com as regras definidas para cada campo, permitindo a autenticação quando os dados forem válidos segundo essas regras.

#### Recuperação de senha

**Descrição:** O sistema deve disponibilizar uma funcionalidade que permita ao usuário iniciar o processo de recuperação de senha pela tela de login.

**Funcionalidades esperadas:**

- Disponibilizar o link "Esqueci minha senha" na tela de login.
- Permitir que o usuário acesse a funcionalidade de recuperação de senha pelo link correspondente.
- Direcionar o usuário para a página ou etapa de recuperação de senha.

**Resultado esperado:** Ao clicar em "Esqueci minha senha", o sistema deve direcionar o usuário para o fluxo de recuperação de senha.

#### Persistência da sessão de login

**Descrição:** O sistema deve permitir que o usuário mantenha sua autenticação ao retornar à aplicação quando a opção "Manter conectado" estiver selecionada, conforme o comportamento previsto para essa funcionalidade.

**Funcionalidades esperadas:**

- Disponibilizar a opção "Manter conectado" na tela de login.
- Considerar a opção selecionada durante o processo de autenticação.
- Manter a autenticação do usuário ao retornar à aplicação, conforme as regras de persistência da sessão.
- Solicitar uma nova autenticação quando não houver uma sessão válida, de acordo com as regras definidas para o sistema.

**Resultado esperado:** Quando a opção "Manter conectado" estiver selecionada, o sistema deve preservar a autenticação conforme o comportamento previsto. Caso não exista uma sessão válida, o usuário deve ser direcionado à tela de login.

#### Controle de acesso às áreas autenticadas e logout

**Descrição:** O sistema deve permitir o acesso ao dashboard somente quando o usuário possuir uma sessão válida e estiver autenticado, e encerrar a sessão no logout.

**Funcionalidades esperadas:**

- Validar a autenticação do usuário ao acessar áreas restritas.
- Verificar a validade da sessão antes de permitir o acesso ao dashboard.
- Impedir o acesso a áreas autenticadas quando o usuário não possuir uma sessão válida.
- Aplicar a validação de acesso mesmo quando o usuário inserir diretamente a URL `/dashboard` na barra de endereços do navegador.
- Redirecionar usuários não autenticados à tela de login.
- Encerrar a sessão ao clicar em sair e exigir novo login para voltar às telas internas.

**Resultado esperado:** O sistema deve permitir o acesso ao dashboard somente para usuários autenticados com uma sessão válida, independentemente de acessarem a área pela navegação da interface ou diretamente pela URL, e voltar para a tela de login depois do logout.

---

### 🏠 RF02 - Página inicial do dashboard

**Cenário de teste:** C02 (`CT_RF02_`)

**Descrição:** Depois do login, o sistema deve exibir a página inicial com o resumo da academia, com saudação, data e indicadores que levam ao detalhe de cada informação.

**Funcionalidades esperadas:**

- Exibir a saudação com o nome da conta autenticada e a data de hoje.
- Exibir o texto "Aqui está o resumo da sua academia hoje".
- Exibir os cards de alunos em risco de evasão, valor em aberto, pico de movimento e avaliações pendentes, cada um com o link "Ver detalhes".
- Exibir os cards Clientes Ativos, Clientes Ausentes, Sem Matrículas, Personais, Matrículas no Período, Desistências no Período e Renovações.
- Abrir o detalhe de cada card (Radar de Evasão, Financeiro em Aberto, clientes ausentes, sem matrícula e desistências), com valores iguais aos do card.
- Filtrar o resumo por período (data inicial e data final), sem aceitar data inicial maior que a final.
- Levar às telas de Avaliações, Inteligência & Automação e Presenças pelos links da página.

**Resultado esperado:** A página inicial abre em `/dashboard` com o nome de quem entrou, e os valores dos cards conferem com as telas de detalhe e com as demais telas do sistema.

---

### 📊 RF03 - Dashboard

**Cenário de teste:** C03 (`CT_RF03_`)

**Descrição:** O sistema deve exibir a página Dashboard com os gráficos de clientes, matrículas, contas a receber, cancelamentos e avaliações, e os indicadores da Inteligência Sifit.

**Funcionalidades esperadas:**

- Abrir o Dashboard pelo menu lateral, na rota `/dash`.
- Exibir o título e o caminho de navegação do Dashboard.
- Exibir os indicadores da Inteligência Sifit: alunos em risco, aniversariantes, avaliações vencendo e frequência em queda, com acesso à tela de Inteligência.
- Exibir os gráficos de Clientes (frequência, idade, sexo), Matrículas (por mês, por plano), Contas a Receber, Cancelamentos e Avaliações.
- Manter os indicadores coerentes com a Página Inicial.

**Resultado esperado:** O Dashboard abre com o título correto, com gráficos legíveis e indicadores iguais aos das demais telas.

---

### 👥 RF04 - Gestão de clientes

**Cenário de teste:** C04 (`CT_RF04_`)

**Descrição:** O sistema deve permitir listar, buscar, filtrar, cadastrar, visualizar, alterar e excluir clientes, validando os campos obrigatórios e os dados informados.

**Funcionalidades esperadas:**

- Listar os clientes com filtros de Código, Nome, Status, Situação, Plano e Personal.
- Exibir os indicadores Clientes Cadastrados, Clientes Ativos, Sem Matrículas e Ausentes.
- Buscar por parte do nome e pelo código (o campo Código aceita só números), informando quando nada for encontrado.
- Paginar a lista de acordo com o resultado do filtro e com a quantidade escolhida por página (20, 50 ou 100).
- Cadastrar cliente em `/adicionar-cliente`, exigindo Nome, Status, Sexo e Data de Nascimento, e recusando data de nascimento futura e CPF inválido.
- Visualizar a ficha do cliente (dados, desempenho e matrícula atual) sem valores nulos ou fictícios.
- Alterar e inativar os dados do cliente e pedir confirmação antes da exclusão.

**Resultado esperado:** A lista, a busca e a paginação refletem o filtro aplicado, o cadastro não segue com obrigatórios vazios ou dados inválidos e as alterações ficam gravadas.

---

### 💳 RF05 - Gestão de planos

**Cenário de teste:** C05 (`CT_RF05_`)

**Descrição:** O sistema deve permitir listar, buscar, filtrar, cadastrar, alterar, inativar e excluir os planos vendidos pela academia.

**Funcionalidades esperadas:**

- Listar os planos com filtros de Código, Nome e Status e os indicadores Planos, Ativos, Alunos em Planos, Receita Estimada e o ranking.
- Exibir na coluna "Alunos" e na receita estimada os valores das matrículas ativas.
- Cadastrar plano com nome, grupo, status, cobrança, parcelas, valor mensal, valor de matrícula, personal, dependentes e benefícios, validando os campos obrigatórios e recusando valores negativos.
- Alterar, inativar e excluir planos.
- Oferecer na matrícula somente os planos ativos.

**Resultado esperado:** O plano só é salvo com os dados exigidos e válidos, as alterações ficam gravadas e o plano inativo deixa de aparecer na matrícula.

---

### 📝 RF06 - Gestão de matrículas

**Cenário de teste:** C06 (`CT_RF06_`)

**Descrição:** O sistema deve permitir listar, buscar, cadastrar, visualizar, cancelar e excluir matrículas vinculadas a clientes.

**Funcionalidades esperadas:**

- Listar matrículas com código, nome, plano e status, e os indicadores Matrículas Ativas, Recorrentes, Não Renovadas e Cadastradas este Mês, com busca e paginação.
- Cadastrar matrícula em `/adicionar-matricula`, exigindo a seleção do cliente, do plano (modalidade) e do tipo de pagamento.
- Aplicar o desconto ao valor total e definir dia de vencimento e quantidade de parcelas, recusando datas inválidas.
- Impedir mais de uma matrícula ativa por cliente.
- Manter as matrículas ativas coerentes com os clientes ativos.
- Visualizar, cancelar e excluir matrículas com confirmação.

**Resultado esperado:** A matrícula só é salva com cliente, plano e pagamento válidos, com o valor correto, e as matrículas ativas pertencem a clientes ativos.

---

### 💰 RF07 - Contas a receber

**Cenário de teste:** C07 (`CT_RF07_`)

**Descrição:** O sistema deve listar, cadastrar, receber e excluir as contas a receber do período e apresentar os totais financeiros.

**Funcionalidades esperadas:**

- Filtrar por código, nome do cliente, tipo de data, período (com atalhos) e status.
- Exibir Entradas, Saídas, Líquido, Previsto para o Mês, Recebido no Mês, Pendentes e Atrasadas.
- Exibir cliente, título, valor a receber, valor recebido e status de cada conta.
- Cadastrar conta validando cliente e valor, e gerar as contas das parcelas a partir da matrícula.
- Registrar o recebimento exigindo o tipo de pagamento e o local, sem aceitar valor maior que o devido sem alerta, e excluir contas.

**Resultado esperado:** Os totais conferem com as contas listadas e o recebimento só é registrado com os dados exigidos.

---

### 🚚 RF08 - Gestão de fornecedores

**Cenário de teste:** C08 (`CT_RF08_`)

**Descrição:** O sistema deve permitir listar, buscar, cadastrar, visualizar, alterar e excluir fornecedores.

**Funcionalidades esperadas:**

- Listar e buscar fornecedores por código e nome, tratando códigos inexistentes.
- Cadastrar fornecedor exigindo o nome ("Informe o nome do fornecedor.").
- Visualizar, alterar e excluir fornecedores, com confirmação antes da exclusão.

**Resultado esperado:** O fornecedor só é salvo com o nome, as alterações ficam gravadas e a exclusão pede confirmação.

---

### 📍 RF09 - Check-in e presenças

**Cenário de teste:** C09 (`CT_RF09_`)

**Descrição:** O sistema deve registrar o check-in dos clientes e exibir os check-ins do dia e as presenças.

**Funcionalidades esperadas:**

- Registrar check-in manual (busca por nome, código, CPF ou telefone) e pela entrada rápida (código do cliente), liberando somente clientes com matrícula ativa e avisando quando o código estiver vazio ou não existir.
- Exibir Check-ins hoje, Presentes agora, Meta do dia, Média diária e Taxa de frequência.
- Listar os check-ins do dia com cliente, plano, horário (no horário local), entrada, saída, unidade e status.
- Exibir o pico de movimento, igual ao da Página Inicial.
- Listar presenças por período em `/presencas`, incluindo os check-ins feitos.

**Resultado esperado:** Os indicadores do Check-in batem com a lista e com as demais telas, e o check-in aparece na tela de Presenças.

---

### 📏 RF10 - Avaliações físicas

**Cenário de teste:** C10 (`CT_RF10_`)

**Descrição:** O sistema deve permitir listar, filtrar, agendar, alterar, registrar e excluir avaliações físicas.

**Funcionalidades esperadas:**

- Listar avaliações com filtros de Código, Nome e Status (Pendente ou Realizado).
- Agendar avaliação exigindo o aluno, o personal, a data e uma hora válida.
- Alterar a data e a hora da avaliação agendada.
- Registrar a avaliação realizada, com cálculo automático e formatado do IMC.
- Excluir avaliações.

**Resultado esperado:** A avaliação só é salva com aluno e hora válidos, e a avaliação realizada fica registrada com o IMC.

---

### 🏋️ RF11 - Turmas e SifitBox

**Cenário de teste:** C11 (`CT_RF11_`)

**Descrição:** O sistema deve permitir manter as turmas e gerar as aulas do SifitBox.

**Funcionalidades esperadas:**

- Listar, buscar e filtrar turmas, com a opção de limpar os filtros.
- Cadastrar turma exigindo nome, plano, dias da semana e horário, com hora final depois da inicial.
- Alterar e excluir turmas.
- Consultar e gerar as aulas do SifitBox por período, informando o resultado.

**Resultado esperado:** A turma só é salva com os dados exigidos e coerentes, e a geração de aulas informa o que foi feito.

---

### 🏧 RF12 - Caixas

**Cenário de teste:** C12 (`CT_RF12_`)

**Descrição:** O sistema deve permitir listar, abrir e fechar caixas.

**Funcionalidades esperadas:**

- Listar caixas por período e status (Aberto ou Fechado), com paginação.
- Exibir Caixas Abertos, Caixas Fechados, Locais de Caixa e Registros no Período.
- Abrir caixa pela ação "Abrir Caixa", exigindo o local de contas e sem permitir dois caixas abertos no mesmo local.
- Fechar o caixa somente depois de buscar e conferir as contas do período.

**Resultado esperado:** O caixa só é aberto com os dados exigidos e o sistema orienta o que falta, sem erro interno, e o fechamento só é gravado com as contas conferidas.

---

### 💸 RF13 - Contas a pagar e despesas fixas

**Cenário de teste:** C13 (`CT_RF13_`)

**Descrição:** O sistema deve permitir cadastrar, listar, pagar e excluir contas a pagar e manter as despesas fixas.

**Funcionalidades esperadas:**

- Filtrar contas a pagar por código, fornecedor ou colaborador, tipo de data, período e status, com os valores a pagar e restantes.
- Cadastrar nova conta pela ação "Nova Conta", informando ao usuário os campos obrigatórios que faltarem.
- Visualizar, registrar o pagamento e excluir contas a pagar.
- Cadastrar, alterar, inativar e excluir despesas fixas com valor positivo e recorrência.

**Resultado esperado:** A conta só é salva com os dados exigidos e o sistema orienta o que falta, sem erro interno, e o pagamento pode ser registrado.

---

### 💪 RF14 - Fichas de treino e exercícios

**Cenário de teste:** C14 (`CT_RF14_`)

**Descrição:** O sistema deve permitir montar fichas de treino e manter a biblioteca de exercícios.

**Funcionalidades esperadas:**

- Cadastrar ficha de treino com aluno, personal, período e objetivo, montar os treinos com exercícios da biblioteca, visualizar e excluir fichas.
- Listar os exercícios por grupo muscular, com o total de cada grupo.
- Cadastrar exercício exigindo o nome, sem duplicidade no mesmo grupo, e alterar e excluir exercícios com confirmação.

**Resultado esperado:** A ficha é salva e pode ser aberta depois, e a biblioteca não aceita exercício sem nome ou repetido.

---

### 🎯 RF15 - Prospecção

**Cenário de teste:** C15 (`CT_RF15_`)

**Descrição:** O sistema deve permitir cadastrar e acompanhar os leads pelos estágios Novo Contato, Interessado, Fez Aula Experimental, Proposta e Fechado.

**Funcionalidades esperadas:**

- Buscar leads por nome, e-mail, telefone ou código e filtrar por estágio, com a opção de limpar.
- Cadastrar lead exigindo o nome e um e-mail válido, sem leads duplicados.
- Alterar o estágio e excluir leads.

**Resultado esperado:** O lead só é salvo com os dados válidos, sem duplicidade, e o estágio alterado fica gravado.

---

### 🧑‍🏫 RF16 - Colaboradores e funções

**Cenário de teste:** C16 (`CT_RF16_`)

**Descrição:** O sistema deve permitir listar, cadastrar, alterar, inativar e excluir colaboradores e manter as funções e suas permissões.

**Funcionalidades esperadas:**

- Listar colaboradores com os indicadores Colaboradores Cadastrados, Ativos e Personais, e buscar por nome e código.
- Cadastrar colaborador em `/adicionar-colaborador`, informando o que faltar.
- Alterar, inativar, vincular funções e excluir colaboradores.
- Cadastrar funções (internas ou externas, personal e avaliador) exigindo o nome, sem duplicidade, filtrar por tipo, alterar, excluir e definir as permissões.

**Resultado esperado:** O colaborador e a função só são salvos com os dados exigidos e o sistema orienta o que falta, sem erro interno.

---

### 🛍️ RF17 - Produtos

**Cenário de teste:** C17 (`CT_RF17_`)

**Descrição:** O sistema deve permitir manter os produtos de venda e de troca por pontos.

**Funcionalidades esperadas:**

- Buscar e filtrar produtos por status e tipo.
- Cadastrar produto de venda com preço positivo e produto de troca por pontos com pontuação, indicando os campos obrigatórios.
- Exibir os valores no formato monetário brasileiro.
- Alterar, inativar e excluir produtos.

**Resultado esperado:** O produto só é salvo com os dados exigidos e válidos, e os valores aparecem em reais.

---

### 🩺 RF18 - Fichas de anamnese

**Cenário de teste:** C18 (`CT_RF18_`)

**Descrição:** O sistema deve permitir aplicar anamneses aos alunos por meio de um assistente.

**Funcionalidades esperadas:**

- Selecionar o aluno, sem avançar enquanto ele não for escolhido.
- Escolher o modelo, exibindo o nome do aluno e as perguntas do modelo.
- Responder às perguntas e finalizar a anamnese.
- Listar as fichas aplicadas, com busca, filtro de status e indicadores.

**Resultado esperado:** A anamnese aplicada aparece na listagem com as respostas do modelo escolhido.

---

### 🗂️ RF19 - Cadastros de apoio

**Cenário de teste:** C19 (`CT_RF19_`)

**Descrição:** O sistema deve permitir cadastrar itens de apoio exigindo o nome. Neste cenário ficam Bandeiras de Cartão, Pontuação, Enquetes, Atividades, Tipos de Documentos, Categorias Crossfit, Objetivos de Treino, Tipos de Pagamento e Perguntas de Anamnese. Planos, Fornecedores, Turmas, Prospecção, Funções, Produtos e Exercícios têm o formulário vazio testado no requisito do próprio módulo (RF05, RF08, RF11, RF15, RF16, RF17 e RF14).

**Funcionalidades esperadas:**

- Abrir o formulário pelo botão de novo cadastro de cada tela.
- Impedir o salvamento quando o nome estiver vazio.
- Informar o campo obrigatório que falta.

**Resultado esperado:** Nenhum registro em branco é criado e o campo obrigatório é indicado.
