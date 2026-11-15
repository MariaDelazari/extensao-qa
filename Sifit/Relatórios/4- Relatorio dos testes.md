# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari, RA: 240017; Ville Nunes Figueiredo da Silva, RA: 14534; Keltton Felipe Alves Silveira, RA: 14509; Daniel Satel Pereira, RA: 14567; Rafael Colombo da Silva, RA: 14551
**Data de execução:** 12/10/2026 a 28/10/2026, e 15/11/2026 para Grupos, Modelos de contrato e Box - Turmas (C20 a C22). Em 24/10/2026, os testes passaram para o endereço indicado abaixo.
**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, Sifit Unialfa.

- Sistema operacional: Ubuntu 26.04 LTS, Linux e Windows 11
- Navegador: Google Chrome 150.0.7871.46 e 155
- URL até dia 23/10/2026 : https://sifit.centrion.com.br/
- URL a partir do dia 24/10/2026: https://sifitalfa.centrion.com.br/

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 250                     | 133            | 117            | 115              |

Os 250 casos estão nos cenários C01 a C22. Um caso falhou quando existe um bug aberto apontando para ele: 117 falharam e 133 passaram. 133 + 117 = 250. O relatório de bugs tem 115 bugs: 113 abertos e 2 em revisão (BUG-025 e BUG-026), que não fazem nenhum caso falhar.

Alguns casos foram executados mais de uma vez, em datas ou endereços diferentes. O resultado do caso junta essas execuções, e a evidência é o vídeo que mostra o resultado registrado. Nos casos C01-CT01, C01-CT02, C02-CT01, C04-CT04, C04-CT10, C06-CT07 e C09-CT03, uma execução passou e outra encontrou a falha; o caso conta como falhou.

Evidências: 152 casos têm vídeo ou print, e 98 aguardam o vídeo (marcados com `[Vídeo](coloque o link do video aqui)`). Dos 115 bugs, 73 têm vídeo ou print, e 42 aguardam o vídeo (`[BUG:NN](coloque o link do video aqui)`). O roteiro está em `5-Roteiro-de-videos.md`.

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                          | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s)                                                                                        |
| --------- | ------------------------------- | -------------- | -------------- | ---------------- | ---------------------------------------------------------------------------------------------------------- |
| RF01      | Login na plataforma             | 9              | 2              | 8                | BUG-001, BUG-002, BUG-003, BUG-004, BUG-005, BUG-006, BUG-007, BUG-011                                     |
| RF02      | Página inicial do dashboard     | 10             | 3              | 9                | BUG-007, BUG-008, BUG-009, BUG-010, BUG-014, BUG-015, BUG-033, BUG-034, BUG-097                            |
| RF03      | Dashboard                       | 4              | 1              | 3                | BUG-012, BUG-013, BUG-014                                                                                  |
| RF04      | Gestão de clientes              | 16             | 4              | 12               | BUG-016, BUG-017, BUG-035, BUG-036, BUG-037, BUG-038, BUG-039, BUG-040, BUG-098, BUG-099, BUG-100, BUG-101 |
| RF05      | Gestão de planos                | 14             | 8              | 6                | BUG-041, BUG-042, BUG-043, BUG-044, BUG-045, BUG-046 (em revisão: BUG-025)                                 |
| RF06      | Gestão de matrículas            | 14             | 4              | 9                | BUG-018, BUG-047, BUG-048, BUG-049, BUG-050, BUG-051, BUG-052, BUG-053, BUG-102                            |
| RF07      | Contas a receber                | 13             | 8              | 5                | BUG-019, BUG-054, BUG-055, BUG-056, BUG-057                                                                |
| RF08      | Gestão de fornecedores          | 9              | 6              | 3                | BUG-058, BUG-059, BUG-060                                                                                  |
| RF09      | Check-in e presenças            | 12             | 4              | 7                | BUG-022, BUG-023, BUG-061, BUG-062, BUG-063, BUG-064, BUG-065                                              |
| RF10      | Avaliações físicas              | 11             | 7              | 5                | BUG-066, BUG-067, BUG-068, BUG-069, BUG-115                                                                |
| RF11      | Turmas e SifitBox               | 13             | 11             | 2                | BUG-070, BUG-071                                                                                           |
| RF12      | Caixas                          | 11             | 6              | 5                | BUG-021, BUG-072, BUG-073, BUG-074, BUG-075                                                                |
| RF13      | Contas a pagar e despesas fixas | 16             | 10             | 6                | BUG-020, BUG-076, BUG-077, BUG-078, BUG-079, BUG-080                                                       |
| RF14      | Fichas de treino e exercícios   | 13             | 8              | 4                | BUG-081, BUG-082, BUG-083, BUG-084                                                                         |
| RF15      | Prospecção                      | 12             | 11             | 1                | BUG-085 (em revisão: BUG-026)                                                                              |
| RF16      | Colaboradores e funções         | 17             | 11             | 6                | BUG-024, BUG-086, BUG-087, BUG-088, BUG-089                                                              |
| RF17      | Produtos                        | 11             | 7              | 4                | BUG-027, BUG-090, BUG-091, BUG-092                                                                         |
| RF18      | Fichas de anamnese              | 7              | 3              | 4                | BUG-093, BUG-094, BUG-095, BUG-096                                                                         |
| RF19      | Cadastros de apoio              | 9              | 4              | 5                | BUG-028, BUG-029, BUG-030, BUG-031, BUG-032                                                                |
| RF20      | Grupos                          | 10             | 7              | 3                | BUG-103, BUG-104, BUG-105                                                                                  |
| RF21      | Modelos de contrato             | 6              | 3              | 3                | BUG-106, BUG-107                                                                                           |
| RF22      | Box - Turmas                    | 13             | 5              | 8                | BUG-108, BUG-109, BUG-110, BUG-111, BUG-112, BUG-113, BUG-114                                              |

O BUG-007 aparece em RF01 e RF02, e o BUG-014 em RF02 e RF03, porque cada um aponta para casos dos dois cenários.

---

## 🐞 **Resumo dos Bugs Reportados**

| ID      | Título                                                                              | Severidade | Status     |
| ------- | ----------------------------------------------------------------------------------- | ---------- | ---------- |
| BUG-001 | Falha no login ao inserir espaços extras nas credenciais válidas                    | Média      | Aberto     |
| BUG-002 | Link "Esqueci minha senha" não funciona                                             | Média      | Aberto     |
| BUG-003 | Erro interno do servidor ao validar credenciais inválidas no login                  | Alta       | Aberto     |
| BUG-004 | Ausência de validação de campos obrigatórios no login                               | Média      | Aberto     |
| BUG-005 | Falha na persistência e no controle da sessão de login                              | Alta       | Aberto     |
| BUG-006 | Erro interno do servidor ao autenticar com credenciais válidas                      | Alta       | Aberto     |
| BUG-007 | Inconsistência na identificação do usuário e na autenticação                        | Média      | Aberto     |
| BUG-008 | Radar de Evasão mostra a faixa errada de alunos                                     | Média      | Aberto     |
| BUG-009 | Cobrança e perfil de Rafael Santos não fecham com a lista                           | Alta       | Aberto     |
| BUG-010 | Card de valor em aberto não confere com o detalhe                                   | Alta       | Aberto     |
| BUG-011 | O campo de senha não deixa ver o que foi digitado                                   | Média      | Aberto     |
| BUG-012 | Dashboard mostra o título "Despesas Fixas"                                          | Média      | Aberto     |
| BUG-013 | Títulos dos gráficos do Dashboard ficam ilegíveis                                   | Baixa      | Aberto     |
| BUG-014 | Quantidade de alunos em risco diverge entre as telas                                | Alta       | Aberto     |
| BUG-015 | Card de avaliações pendentes mostra 1, mas a lista tem 5 pendentes                  | Alta       | Aberto     |
| BUG-016 | Paginação de clientes mostra 3 páginas para 1 resultado                             | Baixa      | Aberto     |
| BUG-017 | Campo Código da busca de clientes aceita letras                                     | Baixa      | Aberto     |
| BUG-018 | Matrículas ativas pertencem a clientes inativos                                     | Alta       | Aberto     |
| BUG-019 | Totais de Contas a Receber não fecham com a listagem                                | Média      | Aberto     |
| BUG-020 | Erro no servidor ao salvar conta a pagar com campos vazios                          | Média      | Aberto     |
| BUG-021 | Erro no servidor ao abrir caixa com campos vazios                                   | Média      | Aberto     |
| BUG-022 | Check-ins do dia não batem com a lista de check-ins                                 | Alta       | Aberto     |
| BUG-023 | Horário de pico diferente entre Página Inicial e Check-in                           | Baixa      | Aberto     |
| BUG-024 | Erro no servidor ao salvar colaborador com campos vazios                            | Média      | Aberto     |
| BUG-025 | Cadastro de Planos não avisa nada ao salvar vazio                                   | Média      | Em revisão |
| BUG-026 | Cadastro de Prospecção não avisa nada ao salvar vazio                               | Média      | Em revisão |
| BUG-027 | Erro genérico ao salvar produto vazio                                               | Baixa      | Aberto     |
| BUG-028 | Erro genérico ao salvar enquete vazia                                               | Baixa      | Aberto     |
| BUG-029 | Atividades permite salvar registro em branco                                        | Média      | Aberto     |
| BUG-030 | Objetivos de Treino permite salvar registro em branco                               | Média      | Aberto     |
| BUG-031 | Tipos de Pagamento permite salvar registro em branco                                | Média      | Aberto     |
| BUG-032 | Erro ao salvar pergunta de anamnese vazia                                           | Média      | Aberto     |
| BUG-033 | Quantidade de clientes ausentes diverge entre a Página Inicial e a tela de Clientes | Média      | Aberto     |
| BUG-034 | Lista de desistências vazia, embora o total informe 3 desistências                  | Média      | Aberto     |
| BUG-035 | Erro ao cadastrar cliente com dados válidos                                         | Crítica    | Aberto     |
| BUG-036 | Busca por código não retorna clientes sem matrícula                                 | Média      | Aberto     |
| BUG-037 | Listagem não respeita a quantidade de registros por página                          | Baixa      | Aberto     |
| BUG-038 | Ausência de mensagem quando a busca não encontra clientes                           | Baixa      | Aberto     |
| BUG-039 | Erro ao salvar alterações dos dados do cliente                                      | Crítica    | Aberto     |
| BUG-040 | Erro no servidor ao acessar cliente excluído                                        | Baixa      | Aberto     |
| BUG-041 | Coluna "Alunos", ranking e receita estimada dos planos exibem valores zerados       | Média      | Aberto     |
| BUG-042 | Busca por código retorna planos cujo código apenas contém o valor informado         | Baixa      | Aberto     |
| BUG-043 | Erro interno com exposição de SQL ao salvar plano sem grupo                         | Média      | Aberto     |
| BUG-044 | Sistema permite cadastrar plano com quantidade de parcelas negativa                 | Média      | Aberto     |
| BUG-045 | Inativação do plano não é salva                                                     | Alta       | Aberto     |
| BUG-046 | Planos inativos são exibidos no cadastro de matrícula                               | Média      | Aberto     |
| BUG-047 | Desconto não é aplicado ao valor total da matrícula                                 | Média      | Aberto     |
| BUG-048 | Mensagem incorreta ao cadastrar matrícula para cliente com matrícula ativa          | Baixa      | Aberto     |
| BUG-049 | Paginação não permite acessar matrículas além da primeira página                    | Média      | Aberto     |
| BUG-050 | Erro no servidor ao excluir matrícula, embora a exclusão seja efetivada             | Média      | Aberto     |
| BUG-051 | Mensagem de validação permanece após selecionar o tipo de pagamento                 | Baixa      | Aberto     |
| BUG-052 | Ausência de mensagem quando a busca não encontra matrículas                         | Baixa      | Aberto     |
| BUG-053 | Campo "Dia Vencimento" aceita data e exibe erro de SQL ao salvar a matrícula        | Média      | Aberto     |
| BUG-054 | Indicador "Contas Atrasadas" diverge do filtro de contas vencidas                   | Média      | Aberto     |
| BUG-055 | Recebimento é registrado sem tipo de pagamento                                      | Média      | Aberto     |
| BUG-056 | Recebimento aceita valor maior que o valor a receber sem alerta                     | Baixa      | Aberto     |
| BUG-057 | Ausência de mensagem quando a busca não encontra contas a receber                   | Baixa      | Aberto     |
| BUG-058 | Busca por código inexistente exibe erro no servidor e mantém todos os fornecedores  | Baixa      | Aberto     |
| BUG-059 | Erro ao cadastrar fornecedor com dados válidos                                      | Alta       | Aberto     |
| BUG-060 | Erro interno com exposição de SQL ao alterar fornecedor                             | Alta       | Aberto     |
| BUG-061 | Check-ins realizados não aparecem na tela de Presenças                              | Alta       | Aberto     |
| BUG-062 | Check-in permanece "Pendente" e não há retorno ao registrar entrada novamente       | Média      | Aberto     |
| BUG-063 | Horário de entrada do check-in exibido com 3 horas a mais                           | Média      | Aberto     |
| BUG-064 | Cliente sem matrícula ativa é liberado para check-in                                | Alta       | Aberto     |
| BUG-065 | Ausência de mensagens no check-in manual e na entrada rápida                        | Baixa      | Aberto     |
| BUG-066 | Erro ao salvar avaliação realizada                                                  | Alta       | Aberto     |
| BUG-067 | Alteração de data e hora da avaliação não é salva                                   | Média      | Aberto     |
| BUG-068 | Cadastro de avaliação aceita hora inválida e retorna erro interno                   | Baixa      | Aberto     |
| BUG-069 | IMC exibido sem formatação                                                          | Baixa      | Aberto     |
| BUG-070 | Erro ao salvar alterações da turma                                                  | Alta       | Aberto     |
| BUG-071 | Cadastro de turma aceita hora final anterior à hora inicial                         | Média      | Aberto     |
| BUG-072 | Fechamento de caixa não é salvo após "Buscar Contas"                                | Alta       | Aberto     |
| BUG-073 | Caixa pode ser fechado sem a conferência das contas                                 | Média      | Aberto     |
| BUG-074 | Sistema permite abrir mais de um caixa no mesmo local                               | Média      | Aberto     |
| BUG-075 | Listagem inicial de caixas ignora o período exibido no filtro                       | Baixa      | Aberto     |
| BUG-076 | Não é possível registrar o pagamento de conta a pagar                               | Alta       | Aberto     |
| BUG-077 | Indicadores "Total a Pagar" e "Valor Restante" exibem zero                          | Média      | Aberto     |
| BUG-078 | Erro no servidor exibido após excluir conta a pagar                                 | Baixa      | Aberto     |
| BUG-079 | Visualização da conta a pagar exibe códigos internos e campos vazios                | Baixa      | Aberto     |
| BUG-080 | Despesa fixa aceita valor negativo e erro interno com valor em texto                | Média      | Aberto     |
| BUG-081 | Ficha de treino não pode ser aberta nem salva                                       | Alta       | Aberto     |
| BUG-082 | Mensagem genérica ao criar ficha sem objetivo do treino                             | Média      | Aberto     |
| BUG-083 | Exclusão de ficha de treino expõe comandos SQL                                      | Média      | Aberto     |
| BUG-084 | Sistema permite cadastrar exercício duplicado no mesmo grupo                        | Baixa      | Aberto     |
| BUG-085 | Sistema permite cadastrar lead duplicado                                            | Baixa      | Aberto     |
| BUG-086 | Busca de colaborador por código inexistente exibe linha vazia                       | Baixa      | Aberto     |
| BUG-087 | Alteração de colaborador expõe comandos SQL                                         | Média      | Aberto     |
| BUG-088 | Funções não podem ser alteradas nem excluídas                                       | Média      | Aberto     |
| BUG-089 | Sistema permite cadastrar função duplicada                                          | Baixa      | Aberto     |
| BUG-090 | Produto do tipo Pontuação não pode ser cadastrado                                   | Alta       | Aberto     |
| BUG-091 | Sistema permite cadastrar produto com preço negativo                                | Média      | Aberto     |
| BUG-092 | Valores dos produtos exibidos sem formatação monetária                              | Baixa      | Aberto     |
| BUG-093 | Anamneses aplicadas não aparecem na listagem                                        | Alta       | Aberto     |
| BUG-094 | Perguntas do modelo de anamnese não são exibidas                                    | Alta       | Aberto     |
| BUG-095 | Assistente de anamnese avança sem aluno e falha com erro interno                    | Média      | Aberto     |
| BUG-096 | Nome do aluno não é exibido na escolha do modelo de anamnese                        | Baixa      | Aberto     |
| BUG-097 | Filtro de período aceita data inicial maior que a final                             | Baixa      | Aberto     |
| BUG-098 | Cadastro de cliente aceita data de nascimento futura                                | Média      | Aberto     |
| BUG-099 | CPF inválido é aceito no cadastro de cliente                                        | Média      | Aberto     |
| BUG-100 | Filtro de status "Ativo" lista clientes inativos                                    | Média      | Aberto     |
| BUG-101 | Ficha do cliente exibe "null" e objetivos fictícios                                 | Baixa      | Aberto     |
| BUG-102 | Campo "Data" da parcela aceita data inválida                                        | Média      | Aberto     |
| BUG-103 | Sistema permite cadastrar grupo duplicado                                           | Baixa      | Aberto     |
| BUG-104 | Status "Inativo" do grupo não é salvo                                               | Média      | Aberto     |
| BUG-105 | Grupo não pode ser excluído                                                         | Média      | Aberto     |
| BUG-106 | Listagem de modelos de contrato aparece vazia                                       | Alta       | Aberto     |
| BUG-107 | Modelo de contrato é salvo sem texto                                                | Baixa      | Aberto     |
| BUG-108 | Box - Turmas não avisa nada ao salvar modalidade ou turma vazia                     | Baixa      | Aberto     |
| BUG-109 | Erro 500 sem mensagem ao cadastrar modalidade duplicada                             | Média      | Aberto     |
| BUG-110 | Turma do Box aceita hora final anterior à hora inicial                              | Média      | Aberto     |
| BUG-111 | Turma do Box é cadastrada sem dias da semana                                        | Média      | Aberto     |
| BUG-112 | Turma do Box aceita quantidade de vagas negativa                                    | Média      | Aberto     |
| BUG-113 | Modalidade inativa aparece no cadastro de turma do Box                              | Baixa      | Aberto     |
| BUG-114 | Exclusão de turma do Box não pede confirmação e mantém a turma na lista             | Média      | Aberto     |
| BUG-115 | Janela "Alterar Data / Hora" aceita data e hora sem formato                         | Média      | Aberto     |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

- Passaram: 133
- Falharam: 117

**Severidade dos bugs abertos:**

- Crítica: 2
- Alta: 23
- Média: 54
- Baixa: 34

**Em revisão:** 2

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
- **BUG-104, BUG-105, BUG-109**: a rota de gravação de grupo ignora o campo de status enviado pela tela; a exclusão de grupo retorna erro 500 (a tela mostra só "Erro ao deletar Grupo") e o cadastro de modalidade duplicada retorna erro 500 sem nenhuma mensagem.
- **BUG-106**: a API retorna os modelos de contrato, mas a tabela renderiza cada linha como um elemento "corpo-modelo" vazio, o que indica que o componente da linha não está registrado no front-end.
- **BUG-108, BUG-110, BUG-111, BUG-112, BUG-113**: o cadastro do Box (SifitBox) não valida os campos na tela e o back-end aceita horário invertido, turma sem dias, vagas negativas e modalidade inativa; o mesmo padrão aparece em Turmas (BUG-071).
- **BUG-114**: a exclusão do Box faz uma inativação (exclusão lógica), mas a listagem de turmas não filtra nem mostra o status.

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
- Casos de teste (C01 a C22); os casos sem vídeo estão marcados com `[Vídeo](coloque o link do video aqui)`. Os cenários com algum caso sem vídeo estão na pasta `Cenarios de testes/Pendentes de evidencias` (C02, C04, C06, C09, C10, C13 a C15, C17 a C19 e C22)
- Relatório de bugs, com o vídeo da falha
- Vídeos no Jam e prints na pasta `Sifit/Evidencias`
- Roteiro dos vídeos a gravar (`5-Roteiro-de-videos.md`)

---

## ✅ **Conclusão**

Dos 250 casos, 133 passaram e 117 falharam, com 115 bugs registrados: 113 abertos e 2 em revisão. No login, só o usuário inexistente e o logout passaram: o login válido mostra erro no servidor ou entra mostrando o nome Jair, a senha incorreta já mostrou erro no servidor, os campos vazios seguem para a API sem aviso, os espaços nas pontas derrubam o login, o link "Esqueci minha senha" não faz nada e a sessão não é controlada.

As falhas mais graves impedem o uso de módulos centrais. Não é possível cadastrar nem alterar clientes (BUG-035 e BUG-039, severidade Crítica) e fornecedores (BUG-059 e BUG-060). A inativação do plano não é salva (BUG-045). O fechamento de caixa com conferência não é gravado (BUG-072). Não há como registrar o pagamento de conta a pagar (BUG-076). A ficha de treino não abre nem salva (BUG-081). A avaliação realizada não é salva (BUG-066). As anamneses aplicadas não aparecem (BUG-093 e BUG-094). Também se repetem formulários vazios que geram erro 500, respostas da API que expõem comandos SQL, registros em branco aceitos (Atividades, Objetivos de Treino e Tipos de Pagamento) e números que mudam de uma tela para outra (alunos em risco, avaliações pendentes, check-ins do dia, matrículas ativas contra clientes ativos e totais de contas a receber).

Funcionam bem a prospecção (11 de 12 casos), as turmas (11 de 13) e a validação do campo obrigatório em Clientes, Matrículas, Avaliações, Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios e Categorias Crossfit.

Ficaram fora do escopo: Pagar.me, WhatsApp e Aplicativo. Ainda não têm caso de teste: Grupos musculares, Modelos de ficha, Configurações, Relatórios, Importar avaliações, Inteligência & Automação, Resultados IA, Local de contas, Bancos, Banco recorrente, Categorias de conta a pagar, Métricas do cliente e Modelos e categorias de anamnese (RF23 a RF33 no plano). O teste de formulário vazio criou 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12), que devem ser excluídos.

Em Grupos, Modelos de contrato e Box - Turmas (C20 a C22, testados em 15/11/2026), os modelos de contrato não aparecem na listagem (BUG-106, severidade Alta), o status "Inativo" do grupo não é salvo (BUG-104) e o grupo não pode ser excluído (BUG-105). O cadastro de turmas do Box aceita horário invertido, turma sem dias e vagas negativas (BUG-110 a BUG-112). Ficaram no ambiente os grupos de teste #8, #9 e #10, que não podem ser excluídos nem inativados, e os modelos de contrato 8 e 9, que não aparecem na listagem. A modalidade e as turmas de teste do Box ficaram inativas.

Até 23/10/2026 os testes usaram https://sifit.centrion.com.br/. A partir de 24/10/2026, usam https://sifitalfa.centrion.com.br/. A versão interna do sistema não foi anotada.
