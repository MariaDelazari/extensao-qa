# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari, RA: 240017; Ville Nunes Figueiredo da Silva, RA: 14534; Keltton Felipe Alves Silveira, RA: 14509; Daniel Satel Pereira, RA: 14567; Rafael Colombo da Silva, RA: 14551
**Data de execução:** 12/10/2026 a 28/10/2026 e 14/11/2026 a 19/11/2026 (Avaliações, Contas a pagar, Grupos, Modelos de contrato, Box - Turmas, Grupos musculares, Modelos de ficha, Configurações, Relatórios, Importar avaliações, Inteligência & Automação / Resultados IA e as telas C29 a C33). Em 24/10/2026, os testes passaram para o endereço indicado abaixo.
**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, Sifit Unialfa.

- Sistema operacional: Ubuntu 26.04 LTS, Linux, Linux Mint e Windows 11
- Navegador: Google Chrome 150.0.7871.46, 155 e 157
- URL até dia 23/10/2026 : https://sifit.centrion.com.br/
- URL a partir do dia 24/10/2026: https://sifitalfa.centrion.com.br/

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 348                     | 181            | 167            | 168              |

Os 348 casos estão nos cenários C01 a C33 (todos os 33 módulos do plano). Um caso falhou quando existe um bug aberto apontando para ele: 167 falharam e 181 passaram. 181 + 167 = 348. O relatório de bugs tem 168 bugs (`BUG-001` a `BUG-169`, sem o número `BUG-125`): 165 abertos e 3 cancelados (BUG-025, BUG-026 e BUG-122), que não fazem nenhum caso falhar.

Alguns casos foram executados mais de uma vez, em datas ou endereços diferentes. O resultado do caso junta essas execuções, e a evidência é o vídeo que mostra o resultado registrado. Nos casos C01-CT01, C01-CT02, C02-CT01, C04-CT04, C04-CT10, C06-CT07 e C09-CT03, uma execução passou e outra encontrou a falha; o caso conta como falhou.

Evidências: todos os 348 casos têm evidência, 342 com vídeo no Jam e 6 com print (C05-CT13, C05-CT14, C09-CT05, C09-CT07, C09-CT08, C14-CT09). Todos os 165 bugs abertos têm evidência: 164 com vídeo e 1 com print (BUG-062).

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                           | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s)                                                                                        |
| --------- | -------------------------------- | -------------- | -------------- | ---------------- | ---------------------------------------------------------------------------------------------------------- |
| RF01      | Login na plataforma              | 10             | 3              | 7                | BUG-001, BUG-002, BUG-003, BUG-004, BUG-005, BUG-006, BUG-007, BUG-011                                     |
| RF02      | Página inicial do dashboard      | 10             | 3              | 7                | BUG-007, BUG-008, BUG-009, BUG-010, BUG-014, BUG-015, BUG-033, BUG-034, BUG-097                            |
| RF03      | Dashboard                        | 4              | 1              | 3                | BUG-012, BUG-013, BUG-014                                                                                  |
| RF04      | Gestão de clientes               | 16             | 4              | 12               | BUG-016, BUG-017, BUG-035, BUG-036, BUG-037, BUG-038, BUG-039, BUG-040, BUG-098, BUG-099, BUG-100, BUG-101 |
| RF05      | Gestão de planos                 | 14             | 8              | 6                | BUG-041, BUG-042, BUG-043, BUG-044, BUG-045, BUG-046 (cancelado: BUG-025)                                  |
| RF06      | Gestão de matrículas             | 16             | 5              | 11               | BUG-018, BUG-047, BUG-048, BUG-049, BUG-050, BUG-051, BUG-052, BUG-053, BUG-102                            |
| RF07      | Contas a receber                 | 13             | 8              | 5                | BUG-019, BUG-054, BUG-055, BUG-056, BUG-057                                                                |
| RF08      | Gestão de fornecedores           | 9              | 6              | 3                | BUG-058, BUG-059, BUG-060                                                                                  |
| RF09      | Check-in e presenças             | 12             | 4              | 8                | BUG-022, BUG-023, BUG-061, BUG-062, BUG-063, BUG-064, BUG-065                                              |
| RF10      | Avaliações físicas               | 12             | 7              | 5                | BUG-066, BUG-067, BUG-068, BUG-069, BUG-115                                                                |
| RF11      | Turmas e SifitBox                | 13             | 11             | 2                | BUG-070, BUG-071                                                                                           |
| RF12      | Caixas                           | 11             | 6              | 5                | BUG-021, BUG-072, BUG-073, BUG-074, BUG-075                                                                |
| RF13      | Contas a pagar e despesas fixas  | 16             | 9              | 7                | BUG-020, BUG-076, BUG-077, BUG-078, BUG-079, BUG-080, BUG-149, BUG-150, BUG-151, BUG-152                   |
| RF14      | Fichas de treino e exercícios    | 13             | 8              | 5                | BUG-081, BUG-082, BUG-083, BUG-084                                                                         |
| RF15      | Prospecção                       | 14             | 12             | 2                | BUG-085, BUG-142 (cancelado: BUG-026)                                                                      |
| RF16      | Colaboradores e funções          | 17             | 11             | 6                | BUG-024, BUG-086, BUG-087, BUG-088, BUG-089                                                                |
| RF17      | Produtos                         | 11             | 7              | 4                | BUG-027, BUG-090, BUG-091, BUG-092                                                                         |
| RF18      | Fichas de anamnese               | 8              | 3              | 5                | BUG-093, BUG-094, BUG-095, BUG-096                                                                         |
| RF19      | Cadastros de apoio               | 12             | 5              | 7                | BUG-028, BUG-029, BUG-030, BUG-031, BUG-032, BUG-133, BUG-134                                              |
| RF20      | Grupos                           | 10             | 7              | 3                | BUG-103, BUG-104, BUG-105                                                                                  |
| RF21      | Modelos de contrato              | 6              | 3              | 3                | BUG-106, BUG-107                                                                                           |
| RF22      | Box - Turmas                     | 13             | 5              | 8                | BUG-108, BUG-109, BUG-110, BUG-111, BUG-112, BUG-113, BUG-114                                              |
| RF23      | Grupos musculares                | 15             | 10             | 5                | BUG-116, BUG-117, BUG-118, BUG-119                                                                         |
| RF24      | Modelos de ficha                 | 8              | 6              | 2                | BUG-120, BUG-121                                                                                           |
| RF25      | Configurações                            | 6              | 4              | 2                | BUG-123, BUG-124 (cancelado: BUG-122)                                                                      |
| RF26      | Relatórios                               | 9              | 3              | 6                | BUG-153, BUG-154, BUG-155, BUG-156, BUG-157, BUG-167                                                       |
| RF27      | Importar avaliações                      | 3              | 1              | 2                | BUG-158, BUG-159, BUG-168                                                                                  |
| RF28      | Inteligência & Automação e Resultados IA | 8              | 2              | 6                | BUG-160, BUG-161, BUG-162, BUG-163, BUG-164, BUG-165, BUG-166, BUG-169                                     |
| RF29      | Local Contas                             | 4              | 1              | 3                | BUG-143, BUG-144, BUG-145, BUG-146                                                                         |
| RF30      | Bancos e Banco Recorrente        | 7              | 3              | 4                | BUG-126, BUG-127, BUG-128, BUG-129                                                                         |
| RF31      | Categorias de conta a pagar      | 5              | 1              | 4                | BUG-126, BUG-130, BUG-131, BUG-132                                                                         |
| RF32      | Métricas do cliente              | 2              | 0              | 2                | BUG-143, BUG-147, BUG-148                                                                                  |
| RF33      | Modelos e categorias de anamnese | 21             | 14             | 7                | BUG-135, BUG-136, BUG-137, BUG-138, BUG-139, BUG-140, BUG-141                                              |

O BUG-007 aparece em RF01 e RF02, o BUG-014 em RF02 e RF03, o BUG-126 em RF30 e RF31 e o BUG-143 em RF29 e RF32, porque cada um aponta para casos de mais de um cenário. A coluna "Bugs encontrados" conta os casos que falharam.

---

## 🐞 **Resumo dos Bugs Reportados**

| ID      | Título                                                                              | Severidade | Status    |
| ------- | ----------------------------------------------------------------------------------- | ---------- | --------- |
| BUG-001 | Falha no login ao inserir espaços extras nas credenciais válidas                    | Média      | Aberto    |
| BUG-002 | Link "Esqueci minha senha" não funciona                                             | Média      | Aberto    |
| BUG-003 | Erro interno do servidor ao validar credenciais inválidas no login                  | Alta       | Aberto    |
| BUG-004 | Ausência de validação de campos obrigatórios no login                               | Média      | Aberto    |
| BUG-005 | Falha na persistência e no controle da sessão de login                              | Alta       | Aberto    |
| BUG-006 | Erro interno do servidor ao autenticar com credenciais válidas                      | Alta       | Aberto    |
| BUG-007 | Inconsistência na identificação do usuário e na autenticação                        | Média      | Aberto    |
| BUG-008 | Radar de Evasão mostra a faixa errada de alunos                                     | Média      | Aberto    |
| BUG-009 | Cobrança e perfil de Rafael Santos não fecham com a lista                           | Alta       | Aberto    |
| BUG-010 | Card de valor em aberto não confere com o detalhe                                   | Alta       | Aberto    |
| BUG-011 | O campo de senha não deixa ver o que foi digitado                                   | Média      | Aberto    |
| BUG-012 | Dashboard mostra o título "Despesas Fixas"                                          | Média      | Aberto    |
| BUG-013 | Títulos dos gráficos do Dashboard ficam ilegíveis                                   | Baixa      | Aberto    |
| BUG-014 | Quantidade de alunos em risco diverge entre as telas                                | Alta       | Aberto    |
| BUG-015 | Card de avaliações pendentes mostra 1, mas a lista tem 5 pendentes                  | Alta       | Aberto    |
| BUG-016 | Paginação de clientes mostra 3 páginas para 1 resultado                             | Baixa      | Aberto    |
| BUG-017 | Campo Código da busca de clientes aceita letras                                     | Baixa      | Aberto    |
| BUG-018 | Matrículas ativas pertencem a clientes inativos                                     | Alta       | Aberto    |
| BUG-019 | Totais de Contas a Receber não fecham com a listagem                                | Média      | Aberto    |
| BUG-020 | Erro no servidor ao salvar conta a pagar com campos vazios                          | Média      | Aberto    |
| BUG-021 | Erro no servidor ao abrir caixa com campos vazios                                   | Média      | Aberto    |
| BUG-022 | Check-ins do dia não batem com a lista de check-ins                                 | Alta       | Aberto    |
| BUG-023 | Horário de pico diferente entre Página Inicial e Check-in                           | Baixa      | Aberto    |
| BUG-024 | Erro no servidor ao salvar colaborador com campos vazios                            | Média      | Aberto    |
| BUG-025 | Cadastro de Planos não avisa nada ao salvar vazio                                   | Média      | Cancelado |
| BUG-026 | Cadastro de Prospecção não avisa nada ao salvar vazio                               | Média      | Cancelado |
| BUG-027 | Erro genérico ao salvar produto vazio                                               | Baixa      | Aberto    |
| BUG-028 | Erro genérico ao salvar enquete vazia                                               | Baixa      | Aberto    |
| BUG-029 | Atividades permite salvar registro em branco                                        | Média      | Aberto    |
| BUG-030 | Objetivos de Treino permite salvar registro em branco                               | Média      | Aberto    |
| BUG-031 | Tipos de Pagamento permite salvar registro em branco                                | Média      | Aberto    |
| BUG-032 | Erro ao salvar pergunta de anamnese vazia                                           | Média      | Aberto    |
| BUG-033 | Quantidade de clientes ausentes diverge entre a Página Inicial e a tela de Clientes | Média      | Aberto    |
| BUG-034 | Lista de desistências vazia, embora o total informe 3 desistências                  | Média      | Aberto    |
| BUG-035 | Erro ao cadastrar cliente com dados válidos                                         | Crítica    | Aberto    |
| BUG-036 | Busca por código não retorna clientes sem matrícula                                 | Média      | Aberto    |
| BUG-037 | Listagem não respeita a quantidade de registros por página                          | Baixa      | Aberto    |
| BUG-038 | Ausência de mensagem quando a busca não encontra clientes                           | Baixa      | Aberto    |
| BUG-039 | Erro ao salvar alterações dos dados do cliente                                      | Crítica    | Aberto    |
| BUG-040 | Erro no servidor ao acessar cliente excluído                                        | Baixa      | Aberto    |
| BUG-041 | Coluna "Alunos", ranking e receita estimada dos planos exibem valores zerados       | Média      | Aberto    |
| BUG-042 | Busca por código retorna planos cujo código apenas contém o valor informado         | Baixa      | Aberto    |
| BUG-043 | Erro interno com exposição de SQL ao salvar plano sem grupo                         | Média      | Aberto    |
| BUG-044 | Sistema permite cadastrar plano com quantidade de parcelas negativa                 | Média      | Aberto    |
| BUG-045 | Inativação do plano não é salva                                                     | Alta       | Aberto    |
| BUG-046 | Planos inativos são exibidos no cadastro de matrícula                               | Média      | Aberto    |
| BUG-047 | Desconto não é aplicado ao valor total da matrícula                                 | Média      | Aberto    |
| BUG-048 | Mensagem incorreta ao cadastrar matrícula para cliente com matrícula ativa          | Baixa      | Aberto    |
| BUG-049 | Paginação não permite acessar matrículas além da primeira página                    | Média      | Aberto    |
| BUG-050 | Erro no servidor ao excluir matrícula, embora a exclusão seja efetivada             | Média      | Aberto    |
| BUG-051 | Mensagem de validação permanece após selecionar o tipo de pagamento                 | Baixa      | Aberto    |
| BUG-052 | Ausência de mensagem quando a busca não encontra matrículas                         | Baixa      | Aberto    |
| BUG-053 | Campo "Dia Vencimento" aceita data e exibe erro de SQL ao salvar a matrícula        | Média      | Aberto    |
| BUG-054 | Indicador "Contas Atrasadas" diverge do filtro de contas vencidas                   | Média      | Aberto    |
| BUG-055 | Recebimento é registrado sem tipo de pagamento                                      | Média      | Aberto    |
| BUG-056 | Recebimento aceita valor maior que o valor a receber sem alerta                     | Baixa      | Aberto    |
| BUG-057 | Ausência de mensagem quando a busca não encontra contas a receber                   | Baixa      | Aberto    |
| BUG-058 | Busca por código inexistente exibe erro no servidor e mantém todos os fornecedores  | Baixa      | Aberto    |
| BUG-059 | Erro ao cadastrar fornecedor com dados válidos                                      | Alta       | Aberto    |
| BUG-060 | Erro interno com exposição de SQL ao alterar fornecedor                             | Alta       | Aberto    |
| BUG-061 | Check-ins realizados não aparecem na tela de Presenças                              | Alta       | Aberto    |
| BUG-062 | Check-in permanece "Pendente" e não há retorno ao registrar entrada novamente       | Média      | Aberto    |
| BUG-063 | Horário de entrada do check-in exibido com 3 horas a mais                           | Média      | Aberto    |
| BUG-064 | Cliente sem matrícula ativa é liberado para check-in                                | Alta       | Aberto    |
| BUG-065 | Ausência de mensagens no check-in manual e na entrada rápida                        | Baixa      | Aberto    |
| BUG-066 | Erro ao salvar avaliação realizada                                                  | Alta       | Aberto    |
| BUG-067 | Alteração de data e hora da avaliação não é salva                                   | Média      | Aberto    |
| BUG-068 | Cadastro de avaliação aceita hora inválida e retorna erro interno                   | Baixa      | Aberto    |
| BUG-069 | IMC exibido sem formatação                                                          | Baixa      | Aberto    |
| BUG-070 | Erro ao salvar alterações da turma                                                  | Alta       | Aberto    |
| BUG-071 | Cadastro de turma aceita hora final anterior à hora inicial                         | Média      | Aberto    |
| BUG-072 | Fechamento de caixa não é salvo após "Buscar Contas"                                | Alta       | Aberto    |
| BUG-073 | Caixa pode ser fechado sem a conferência das contas                                 | Média      | Aberto    |
| BUG-074 | Sistema permite abrir mais de um caixa no mesmo local                               | Média      | Aberto    |
| BUG-075 | Listagem inicial de caixas ignora o período exibido no filtro                       | Baixa      | Aberto    |
| BUG-076 | Não é possível registrar o pagamento de conta a pagar                               | Alta       | Aberto    |
| BUG-077 | Indicadores "Total a Pagar" e "Valor Restante" exibem zero                          | Média      | Aberto    |
| BUG-078 | Erro no servidor exibido após excluir conta a pagar                                 | Baixa      | Aberto    |
| BUG-079 | Visualização da conta a pagar exibe códigos internos e campos vazios                | Baixa      | Aberto    |
| BUG-080 | Despesa fixa aceita valor negativo e erro interno com valor em texto                | Média      | Aberto    |
| BUG-081 | Ficha de treino não pode ser aberta nem salva                                       | Alta       | Aberto    |
| BUG-082 | Mensagem genérica ao criar ficha sem objetivo do treino                             | Média      | Aberto    |
| BUG-083 | Exclusão de ficha de treino expõe comandos SQL                                      | Média      | Aberto    |
| BUG-084 | Sistema permite cadastrar exercício duplicado no mesmo grupo                        | Baixa      | Aberto    |
| BUG-085 | Sistema permite cadastrar lead duplicado                                            | Baixa      | Aberto    |
| BUG-086 | Busca de colaborador por código inexistente exibe linha vazia                       | Baixa      | Aberto    |
| BUG-087 | Alteração de colaborador expõe comandos SQL                                         | Média      | Aberto    |
| BUG-088 | Funções não podem ser alteradas nem excluídas                                       | Média      | Aberto    |
| BUG-089 | Sistema permite cadastrar função duplicada                                          | Baixa      | Aberto    |
| BUG-090 | Produto do tipo Pontuação não pode ser cadastrado                                   | Alta       | Aberto    |
| BUG-091 | Sistema permite cadastrar produto com preço negativo                                | Média      | Aberto    |
| BUG-092 | Valores dos produtos exibidos sem formatação monetária                              | Baixa      | Aberto    |
| BUG-093 | Anamneses aplicadas não aparecem na listagem                                        | Alta       | Aberto    |
| BUG-094 | Perguntas do modelo de anamnese não são exibidas                                    | Alta       | Aberto    |
| BUG-095 | Assistente de anamnese avança sem aluno e falha com erro interno                    | Média      | Aberto    |
| BUG-096 | Nome do aluno não é exibido na escolha do modelo de anamnese                        | Baixa      | Aberto    |
| BUG-097 | Filtro de período aceita data inicial maior que a final                             | Baixa      | Aberto    |
| BUG-098 | Cadastro de cliente aceita data de nascimento futura                                | Média      | Aberto    |
| BUG-099 | CPF inválido é aceito no cadastro de cliente                                        | Média      | Aberto    |
| BUG-100 | Filtro de status "Ativo" lista clientes inativos                                    | Média      | Aberto    |
| BUG-101 | Ficha do cliente exibe "null" e objetivos fictícios                                 | Baixa      | Aberto    |
| BUG-102 | Campo "Data" da parcela aceita data inválida                                        | Média      | Aberto    |
| BUG-103 | Sistema permite cadastrar grupo duplicado                                           | Baixa      | Aberto    |
| BUG-104 | Status "Inativo" do grupo não é salvo                                               | Média      | Aberto    |
| BUG-105 | Grupo não pode ser excluído                                                         | Média      | Aberto    |
| BUG-106 | Listagem de modelos de contrato aparece vazia                                       | Alta       | Aberto    |
| BUG-107 | Modelo de contrato é salvo sem texto                                                | Baixa      | Aberto    |
| BUG-108 | Box - Turmas não avisa nada ao salvar modalidade ou turma vazia                     | Baixa      | Aberto    |
| BUG-109 | Erro 500 e mensagem genérica ao cadastrar modalidade duplicada                      | Média      | Aberto    |
| BUG-110 | Turma do Box aceita hora final anterior à hora inicial                              | Média      | Aberto    |
| BUG-111 | Turma do Box é cadastrada sem dias da semana                                        | Média      | Aberto    |
| BUG-112 | Turma do Box aceita quantidade de vagas negativa                                    | Média      | Aberto    |
| BUG-113 | Modalidade inativa aparece no cadastro de turma do Box                              | Baixa      | Aberto    |
| BUG-114 | Exclusão de turma do Box não pede confirmação e mantém a turma na lista             | Média      | Aberto    |
| BUG-115 | Janela "Alterar Data / Hora" aceita data e hora sem formato                         | Média      | Aberto    |
| BUG-116 | Cadastro de grupo muscular sem tipo de membro mostra erro genérico                  | Baixa      | Aberto    |
| BUG-117 | Grupo muscular é salvo sem nome                                                     | Média      | Aberto    |
| BUG-118 | Grupo muscular duplicado é aceito                                                   | Baixa      | Aberto    |
| BUG-119 | Exclusão de grupo muscular com exercícios mostra erro genérico                      | Baixa      | Aberto    |
| BUG-120 | Não é possível criar modelo de ficha                                                | Alta       | Aberto    |
| BUG-121 | "Alterar" do modelo de ficha abre a ficha de treino de um aluno                     | Alta       | Aberto    |
| BUG-122 | Configurações não confirmam o salvamento                                            | Baixa      | Cancelado |
| BUG-123 | "Dias para contar cliente como ausente" aceita valor negativo                       | Média      | Aberto    |
| BUG-124 | Senha da biometria e token do Pagar.me aparecem em texto aberto                     | Média      | Aberto    |
| BUG-126 | Telas de bancos e de categorias de conta a pagar não estão no menu                  | Média      | Aberto    |
| BUG-127 | Banco é salvo sem nome                                                              | Baixa      | Aberto    |
| BUG-128 | Banco duplicado é aceito                                                            | Baixa      | Aberto    |
| BUG-129 | Excluir banco chama a exclusão de tipo de pagamento                                 | Crítica    | Aberto    |
| BUG-130 | Listagem de categorias de conta a pagar aparece vazia                               | Alta       | Aberto    |
| BUG-131 | Categoria de conta a pagar é salva sem nome                                         | Baixa      | Aberto    |
| BUG-132 | Categoria de conta a pagar duplicada é aceita                                       | Baixa      | Aberto    |
| BUG-133 | Bandeira cadastrada não aparece na listagem                                         | Alta       | Aberto    |
| BUG-134 | Pontuação aceita data final anterior à inicial                                      | Média      | Aberto    |
| BUG-135 | Indicador "Com perguntas" mostra o total de categorias                              | Média      | Aberto    |
| BUG-136 | Categoria de anamnese duplicada é aceita                                            | Baixa      | Aberto    |
| BUG-137 | Edição do modelo não mostra a pergunta obrigatória e apaga a marcação               | Média      | Aberto    |
| BUG-138 | Preview do modelo de anamnese não mostra as perguntas                               | Média      | Aberto    |
| BUG-139 | Modelo de anamnese é salvo sem nenhuma pergunta                                     | Baixa      | Aberto    |
| BUG-140 | Pergunta obrigatória da anamnese pode ficar sem resposta                            | Média      | Aberto    |
| BUG-141 | Modelo de anamnese já aplicado pode ser excluído                                    | Média      | Aberto    |
| BUG-142 | Telefone do lead aceita letras                                                      | Média      | Aberto    |
| BUG-143 | Telas Local Contas e Métricas de Clientes não estão no menu                         | Média      | Aberto    |
| BUG-144 | Listagem de Local Contas fica vazia                                                 | Alta       | Aberto    |
| BUG-145 | Cadastro de Local Contas usa o formulário de Despesas Fixas e dá erro               | Alta       | Aberto    |
| BUG-146 | Erro no servidor ao salvar Local Contas com campos vazios                           | Média      | Aberto    |
| BUG-147 | Métricas de Clientes não exibe as métricas                                          | Alta       | Aberto    |
| BUG-148 | Listas de Métricas de Clientes aparecem abertas, vazias e não fecham                | Média      | Aberto    |
| BUG-149 | Despesa fixa não salva quando o valor é informado com vírgula (aceita apenas ponto) | Média      | Aberto    |
| BUG-150 | Visualização de conta a pagar com legibilidade ruim no modo escuro                  | Baixa      | Aberto    |
| BUG-151 | Menu lateral perde a posição de rolagem e volta ao topo a cada atualização          | Baixa      | Aberto    |
| BUG-152 | Ausência de paginação na listagem de Despesas Fixas                                                                           | Baixa      | Aberto    |
| BUG-153 | Relatórios de Avaliações, Clientes, Colaboradores e Caixas (Normal) retornam resposta vazia e baixam PDF corrompido (0 bytes) | Crítica    | Aberto    |
| BUG-154 | Filtro "Tipo de Plano" no relatório de Matrículas não é enviado na requisição                                                 | Alta       | Aberto    |
| BUG-155 | Erro HTTP 500 ao gerar relatório com datas vazias apesar do indicador "Periodo: Todos"                                        | Alta       | Aberto    |
| BUG-156 | Tela de Relatórios não valida intervalo invertido (Data Início maior que Data Fim)                                            | Média      | Aberto    |
| BUG-157 | Textos sem acentuação na tela de Relatórios e opções em branco em "Tipo de Pagamento"                                         | Baixa      | Aberto    |
| BUG-158 | Tela "Importar Avaliações" não oferece planilha modelo nem lista as colunas obrigatórias                                      | Média      | Aberto    |
| BUG-159 | Breadcrumb incompleto e ausência de botão "Voltar" em "Importar Avaliações"                                                   | Baixa      | Aberto    |
| BUG-160 | Inconsistência nos contadores de alunos em risco e período em "Resultados IA"                                                 | Alta       | Aberto    |
| BUG-161 | "Ver resultados" de Risco de Evasão indica 1 aluno em médio risco, mas exibe lista vazia                                      | Alta       | Aberto    |
| BUG-162 | Modal "Configurar" de Aniversariantes exibe campos e prévia de Risco de Evasão e omite destinatário "Aluno"                   | Alta       | Aberto    |
| BUG-163 | Execuções duplicadas no mesmo minuto em "Atividade recente" inflam métricas de automações                                     | Média      | Aberto    |
| BUG-164 | Coluna "Atividade recente" em Inteligência & Automação não possui barra de rolagem interna                                    | Média      | Aberto    |
| BUG-165 | Canal "Apenas painel" pode ser marcado junto com "WhatsApp" e "E-mail" nas configurações de automação                         | Média      | Aberto    |
| BUG-166 | Divergências entre métricas e status de automações em "Resultados IA" e "Central de Automações"                               | Média      | Aberto    |
| BUG-167 | Campos de data em Relatórios aceitam anos irreais (ex.: 14500) sem validação e imprimem no PDF                                | Média      | Aberto    |
| BUG-168 | Contraste muito baixo e legibilidade ruim no modo escuro em "Importar Avaliações"                                             | Média      | Aberto    |
| BUG-169 | Erro no servidor ao alterar rapidamente a data no painel "Financeiro do dia"                                                  | Média      | Aberto    |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

- Passaram: 181
- Falharam: 167

**Severidade dos bugs abertos:**

- Crítica: 4
- Alta: 35
- Média: 78
- Baixa: 48

**Em revisão:** 0. **Cancelados:** 3 (BUG-025 e BUG-026, os vídeos mostraram o aviso "Preencha este campo."; BUG-122, o vídeo do C25-CT04 mostra a confirmação "Configurações salvas").

---

## 🔍 **Identificação da Causa Raiz (Root Cause Analysis)**

As hipóteses abaixo foram levantadas a partir do comportamento na tela, do console do navegador e das respostas da API (DevTools). São hipóteses, não confirmações do código do sistema.

- **BUG-014, BUG-033, BUG-034**: cada tela calcula os indicadores com regras ou consultas diferentes (ex.: "ausente" na Página Inicial considera quem nunca visitou, e a tela de Clientes não), o que indica a ausência de uma regra única de cálculo.
- **BUG-013**: o console do navegador registra o erro "Invalid scale configuration for scale: yAxes", indicando configuração desatualizada da biblioteca de gráficos, e as cores dos títulos não foram ajustadas ao tema dos cartões.
- **BUG-035, BUG-039**: as rotas de cadastro e de atualização de cliente retornam erro 500 ("Erro interno inesperado.") mesmo com dados válidos, o que indica uma falha comum no back-end, como erro de persistência no banco de dados ou de tratamento dos campos enviados.
- **BUG-036**: a busca por código funciona apenas para clientes com matrícula. A hipótese foi confirmada durante os testes de matrículas: após matricular a cliente 408, ela passou a ser encontrada pela busca por código, o que indica que a consulta depende do vínculo com a matrícula.
- **BUG-016, BUG-037**: a quantidade de páginas parece ser calculada sobre o total de clientes, sem considerar o filtro aplicado, e o limite por página não é aplicado no primeiro carregamento.
- **BUG-040**: o sistema não trata o caso de cliente inexistente e retorna erro 500 em vez de uma mensagem de "cliente não encontrado".
- **BUG-043, BUG-044**: o back-end não valida os campos do plano antes de gravar no banco de dados; o erro de restrição do banco é devolvido diretamente na resposta da API.
- **BUG-045**: o status "inativo" é enviado corretamente pela tela, mas não é gravado, o que indica que a rota de atualização ignora o campo de status.
- **BUG-047**: o campo "Desconto" exibido na visualização recebe o valor da parcela, o que sugere que o campo errado é gravado ou lido, e o valor total não é recalculado na tela de cadastro.
- **BUG-048, BUG-050**: a API retorna o motivo correto ("Já existe matrícula ativa") ou realiza a operação, mas a tela exibe uma mensagem genérica de erro, indicando falha no tratamento das respostas da API.
- **BUG-049**: a quantidade de páginas não é calculada a partir do total de matrículas, impedindo a navegação além da primeira página.
- **BUG-055, BUG-056**: o formulário de recebimento não valida os campos antes do envio e o back-end aceita os dados sem validação.
- **BUG-059, BUG-060**: a atualização do fornecedor não envia o campo "tipo_pessoa" (Física/Jurídica), que é obrigatório no banco de dados; o mesmo padrão de erro 500 no cadastro e na alteração ocorre em Clientes (BUG-035 e BUG-039), o que sugere uma falha comum nas rotas de gravação de cadastros.
- **BUG-061, BUG-062, BUG-063, BUG-064**: o check-in é gravado em uma tabela própria (a API retorna o código do check-in), mas não gera o registro de presença nem atualiza o status; o horário é armazenado em UTC e exibido sem conversão para o fuso de Brasília; a liberação do check-in não consulta a situação da matrícula do cliente.
- **BUG-066, BUG-067, BUG-068**: a rota de registro da avaliação retorna erro 500 mesmo com dados válidos, o botão "Salvar" da alteração de data e hora não dispara nenhuma requisição e os campos de hora não são validados na tela antes do envio.
- **BUG-070, BUG-071**: a rota de atualização de turma retorna erro 500 mesmo sem alterações, o que indica falha no back-end independente dos dados enviados; o horário não é validado nem na tela nem no back-end.
- **BUG-021, BUG-072, BUG-073, BUG-074**: o fluxo de fechamento não valida se as contas foram conferidas e deixa de enviar o fechamento após a busca das contas; a abertura não verifica se já existe caixa aberto para o local nem valida o local antes do envio.
- **BUG-020, BUG-076, BUG-077, BUG-078, BUG-079, BUG-080**: a tela de contas a pagar não implementa a ação de pagamento nem calcula os indicadores de valores; os formulários de contas a pagar e despesas fixas não validam os campos na tela e o back-end aceita valores negativos ou devolve erro 500 para dados inválidos.
- **BUG-081, BUG-083**: o banco de dados de homologação não possui a coluna "descanso_padrao" utilizada pela consulta da ficha, o que indica migração de banco não aplicada no ambiente; a rota de exclusão devolve a saída de depuração do SQL na resposta.
- **BUG-024**: os campos de seleção exibem a primeira opção visualmente, mas o valor vinculado ao formulário permanece vazio, e o back-end não valida esses campos antes de gravar; o mesmo padrão de erro 500 em cadastros ocorre em Clientes (BUG-035) e Fornecedores (BUG-059).
- **BUG-083, BUG-087**: as rotas de exclusão de ficha e de atualização de colaborador devolvem a saída de depuração do SQL, o que indica modo de depuração ativo no back-end de homologação.
- **BUG-027, BUG-090**: o back-end grava o campo "valor" mesmo para produtos de pontuação e não trata o valor vazio, devolvendo o erro do banco de dados ("Data truncated for column 'valor'") na resposta.
- **BUG-093, BUG-094, BUG-095**: a listagem consulta as fichas com o parâmetro "id" nulo; o assistente não carrega as perguntas do modelo e não valida o aluno antes de avançar, enviando a anamnese sem respostas ou sem aluno.
- **BUG-104, BUG-105, BUG-109**: a rota de gravação de grupo ignora o campo de status enviado pela tela; a exclusão de grupo retorna erro 500 (a tela mostra só "Erro ao deletar Grupo") e o cadastro de modalidade duplicada retorna erro 500 e a tela mostra só "Erro ao salvar modalidade".
- **BUG-106**: a API retorna os modelos de contrato, mas a tabela renderiza cada linha como um elemento "corpo-modelo" vazio, o que indica que o componente da linha não está registrado no front-end.
- **BUG-108, BUG-110, BUG-111, BUG-112, BUG-113**: o cadastro do Box (SifitBox) não valida os campos na tela e o back-end aceita horário invertido, turma sem dias, vagas negativas e modalidade inativa; o mesmo padrão aparece em Turmas (BUG-071).
- **BUG-114**: a exclusão do Box faz uma inativação (exclusão lógica), mas a listagem de turmas não filtra nem mostra o status.
- **BUG-126, BUG-129**: as telas de Bancos, Banco Recorrente e Categorias de conta a pagar parecem copiadas de outras telas e não foram terminadas: não estão no menu, abrem fora do layout e a exclusão de banco usa a rota e a mensagem de Tipos de Pagamento.
- **BUG-127, BUG-128, BUG-131, BUG-132**: o back-end de bancos e categorias aceita nome vazio e nome duplicado, e a tela não valida nada antes de enviar.
- **BUG-130**: a API retorna as categorias, mas a tabela da tela não as renderiza.
- **BUG-153, BUG-154, BUG-155, BUG-156, BUG-157, BUG-167**: na tela de Relatórios (`/relatorios`), 4 modelos retornam corpo vazio (`text/html`, 0 bytes) em `POST /api/relatorio/1` e o front-end não verifica o `Content-Type` antes de criar o Blob PDF; o filtro `Tipo de Plano` de Matrículas não é serializado no payload; datas vazias chegam como string vazia e causam HTTP 500 apesar de a tela indicar `Periodo: Todos`; não há validação de intervalo invertido nem de faixa máxima de ano (aceitando `14500`). Como melhoria adicional de UX, os cards estáticos do topo (`Relatorios: 7`, `Saida: PDF`) quase não mudam e agregam pouco valor.
- **BUG-158, BUG-159, BUG-168**: em Importar Avaliações (`/importar-avaliacoes`), falta validação do cabeçalho do Fineshape (planilha aleatória avança para `2 Conferência`) e falta planilha modelo/referência de colunas; o tema escuro não ajusta adequadamente as cores do stepper e da tabela de conferência (mesmo problema de contraste visto em `BUG-150`).
- **BUG-160, BUG-161, BUG-162, BUG-163, BUG-164, BUG-165, BUG-166, BUG-169**: em Inteligência & Automação e Resultados IA, há divergência entre as consultas dos resumos e das listas (`Ver resultados` devolve `resumo.medio: 1` com `alunos: []`; `Resultados IA` mostra `0` em risco e `1` avaliação vencendo contra `0` em `Verificar agora`), o modal `Configurar` de Aniversariantes reutiliza o componente/preview de Risco de Evasão, não há debounce/lock contra execuções duplicadas no mesmo minuto nem na troca rápida de datas em `Financeiro do dia` (`BUG-169`), e faltam paginação em `O que o Sifit identificou` e scroll interno em `Atividade recente`.

| Grupo de bugs                                                          | Causa raiz provável                                                                                                                  |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-004, BUG-043, BUG-065, BUG-084, BUG-098, BUG-099, BUG-102, BUG-115 | Validações ausentes ou parciais no front-end e sem regra no back-end (dados inválidos chegam ao banco; campo faltante gera HTTP 500) |
| BUG-016, BUG-100                                                       | Filtros não enviados na listagem inicial e na troca de página                                                                        |
| BUG-010, BUG-019, BUG-062                                              | Indicadores calculados com consulta diferente da usada nas listagens                                                                 |
| BUG-063                                                                | Data e hora gravadas em UTC sem conversão para America/Sao_Paulo                                                                     |
| BUG-101                                                                | Componentes da ficha com valores fixos (mock) e campos nulos exibidos como "null"                                                    |
| BUG-002, BUG-046, BUG-097                                              | Regras de negócio não implementadas (recuperação de senha, filtro de plano ativo, validação de período)                              |

No banco (MySQL Workbench, somente leitura), o cliente de teste aparece gravado. A coluna `cpf` da tabela `pessoas` é guardada criptografada, por isso a validação do CPF inválido (BUG-099) foi feita pela tela de edição.

---

## 📁 **Evidências e Documentos**

- Plano de Testes
- Análise de requisitos
- Casos de teste (C01 a C33), todos com evidência: vídeo no Jam ou print. A pasta `Cenarios de testes/Pendentes de evidencias` ficou vazia
- Relatório de bugs, com o vídeo da falha
- Vídeos no Jam e prints na pasta `Sifit/Evidencias`

---

## ✅ **Conclusão**

Dos 348 casos distribuídos nos 33 cenários (C01 a C33), 181 passaram e 167 falharam, com 168 bugs registrados: 165 abertos e 3 cancelados (`BUG-025`, `BUG-026` e `BUG-122`). No login, o duplo clique em Entrar (`C01-CT10`), o usuário inexistente e o logout passaram, mas o login válido já mostrou erro no servidor ou entra mostrando o nome Jair, a senha incorreta já mostrou erro no servidor, os campos vazios seguem para a API sem aviso, os espaços nas pontas derrubam o login, o link "Esqueci minha senha" não faz nada e a sessão não é controlada.

As falhas mais graves impedem o uso de módulos centrais. Não é possível cadastrar nem alterar clientes (BUG-035 e BUG-039, severidade Crítica) e fornecedores (BUG-059 e BUG-060). A inativação do plano não é salva (BUG-045). O fechamento de caixa com conferência não é gravado (BUG-072). Não há como registrar o pagamento de conta a pagar (BUG-076). A ficha de treino não abre nem salva (BUG-081). A avaliação realizada não é salva (BUG-066). As anamneses aplicadas não aparecem (BUG-093 e BUG-094). Em Relatórios, 4 dos 7 modelos baixam arquivos PDF corrompidos de 0 bytes sem aviso (BUG-153, severidade Crítica). Também se repetem formulários vazios que geram erro 500, respostas da API que expõem comandos SQL, registros em branco aceitos (Atividades, Objetivos de Treino e Tipos de Pagamento), ausência de paginação em listagens longas (Despesas Fixas e Resultados IA), baixo contraste no modo escuro (Contas a Pagar e Importar Avaliações) e números que mudam de uma tela para outra (alunos em risco, avaliações pendentes/vencendo, check-ins do dia, matrículas ativas contra clientes ativos e totais de contas a receber).

Funcionam bem a prospecção (12 de 14 casos), as turmas (11 de 13), a rejeição de extensão inválida (`.pdf`) em Importar Avaliações e a validação do campo obrigatório em Clientes, Matrículas, Avaliações, Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios e Categorias Crossfit.

Ficaram fora do escopo: Pagar.me, WhatsApp e Aplicativo. Todos os 33 módulos previstos no plano (RF01 a RF33) possuem cenários executados e evidenciados. O teste de formulário vazio criou 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12), que devem ser excluídos.

Em Grupos, Modelos de contrato e Box - Turmas (C20 a C22, testados em 15/11/2026), os modelos de contrato não aparecem na listagem (BUG-106, severidade Alta), o status "Inativo" do grupo não é salvo (BUG-104) e o grupo não pode ser excluído (BUG-105). O cadastro de turmas do Box aceita horário invertido, turma sem dias e vagas negativas (BUG-110 a BUG-112). Ficaram no ambiente os grupos de teste #8, #9 e #10, que não podem ser excluídos nem inativados, e os modelos de contrato 8 e 9, que não aparecem na listagem. A modalidade e as turmas de teste do Box ficaram inativas.

Em Grupos musculares, Modelos de ficha e Configurações (C23 a C25, testados em 15/11/2026), o cadastro de grupo muscular aceita grupo sem nome e duplicado (BUG-117 e BUG-118) e mostra só mensagens genéricas de erro (BUG-116 e BUG-119). Não é possível criar modelo de ficha (BUG-120), e "Alterar" do modelo abre a ficha de treino de um aluno (BUG-121). Em Configurações, os dias para contar cliente como ausente aceitam valor negativo (BUG-123), e a senha da biometria e o token do Pagar.me aparecem em texto aberto (BUG-124). O BUG-122 foi cancelado: o vídeo do C25-CT04 mostra a confirmação "Configurações salvas".

Em Avaliações e Contas a pagar (C10 e C13, gravados em 19/11/2026), a despesa fixa não é salva quando o valor é informado com vírgula (BUG-149), a visualização da conta a pagar fica ilegível no modo escuro (BUG-150), o menu lateral volta ao topo a cada atualização (BUG-151) e a listagem de despesas fixas não tem paginação (BUG-152). Também foram gravados o duplo clique em Entrar (C01-CT10) e a data de término anterior à de início na matrícula (C06-CT15), que passaram.

Em Bancos, Banco Recorrente e Categorias de conta a pagar (C30 e C31, testados em 15/11/2026), as três telas não têm item no menu e só abrem pelo link (BUG-126). O botão de excluir banco chama a exclusão de Tipo de Pagamento com o id do banco (BUG-129, severidade Crítica): no teste, só não apagou o tipo de pagamento 11 porque ele estava em uso. A listagem de categorias fica vazia (BUG-130), e as duas telas aceitam registros sem nome e duplicados. Na gravação do C30-CT07, a exclusão do Banco Brasil mostrou "Erro ao deletar tipo de pagamento", e o tipo de pagamento 1 (Dinheiro) continuou cadastrado. Como a exclusão de banco não é segura, os registros de teste não foram excluídos: bancos 8 a 17 e categorias 25 a 29 e as gravadas nos vídeos.

Em Local Contas e Métricas do cliente (C29 e C32, testados em 15/11/2026), as duas telas não têm item no menu e abrem sem o menu lateral (BUG-143). Local Contas não funciona: a listagem fica vazia embora a API devolva 4 locais (BUG-144) e o formulário da tela é o de Despesas Fixas, que responde erro 500 com a mensagem "Erro ao deletar Despesa" (BUG-145 e BUG-146). Métricas do cliente não mostra nenhuma métrica nem gráfico, embora a API devolva os números (BUG-147), e as listas de clientes aparecem abertas, vazias e não fecham (BUG-148).

Em Relatórios, Importar avaliações e Inteligência & Automação / Resultados IA (C26 a C28, testados em 19/11/2026), quatro modelos de relatório (`Avaliacoes`, `Clientes`, `Colaboradores` e `Caixas` Normal) baixam PDF de 0 bytes corrompido sem aviso (BUG-153, severidade Crítica), datas vazias geram HTTP 500 mesmo exibindo `Periodo: Todos` (BUG-155), o filtro `Tipo de Plano` em Matrículas não é enviado à API (BUG-154) e datas aceitam período invertido e anos irreais como `14500` (BUG-156 e BUG-167). Em Importar Avaliações, arquivos `.pdf` são rejeitados corretamente, mas não há planilha modelo nem validação de cabeçalho do Fineshape (BUG-158), falta botão `Voltar`/breadcrumb completo (BUG-159) e o contraste no modo escuro compromete a leitura (BUG-168). Em Inteligência & Automação e Resultados IA, os contadores de risco e avaliações vencendo divergem entre si e com a lista `Ver resultados` vazia (BUG-160, BUG-161 e BUG-166), o modal `Configurar` de Aniversariantes exibe campos e prévia de Risco de Evasão (BUG-162), há execuções duplicadas no mesmo minuto em `Atividade recente` sem barra de rolagem interna (BUG-163 e BUG-164), `Apenas painel` pode ser marcado junto com WhatsApp/E-mail (BUG-165) e alternar datas rapidamente em `Financeiro do dia` exibe erro no servidor (BUG-169).

Até 23/10/2026 os testes usaram https://sifit.centrion.com.br/. A partir de 24/10/2026, usam https://sifitalfa.centrion.com.br/. A versão interna do sistema não foi anotada.
