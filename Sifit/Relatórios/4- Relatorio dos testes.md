# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari, RA: 240017; Ville Nunes Figueiredo da Silva, RA: 14534; Keltton Felipe Alves Silveira, RA: 14509; Daniel Satel Pereira, RA: 14567; Rafael Colombo da Silva, RA: 14551
**Data de execução:** 12/10/2026 a 28/10/2026. Em 24/10/2026, os testes passaram para o endereço indicado abaixo.
**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, Sifit Unialfa.

- Sistema operacional: Ubuntu 26.04 LTS, Linux e Windows 11
- Navegador: Google Chrome 150.0.7871.46 e 155
- URL até dia 23/10/2026 : https://sifit.centrion.com.br/
- URL a partir do dia 24/10/2026: https://sifitalfa.centrion.com.br/

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 221                     | 116            | 105            | 105              |

Os 221 casos estão nos cenários C01 a C19. Um caso falhou quando existe um bug aberto apontando para ele: 105 falharam e 116 passaram. 116 + 105 = 221. O relatório de bugs tem 105 bugs: 102 abertos e 3 em revisão (BUG-025, BUG-026 e BUG-027), que não fazem nenhum caso falhar.

Alguns casos foram executados mais de uma vez, em datas ou endereços diferentes. O resultado do caso junta essas execuções, e a evidência é o vídeo que mostra o resultado registrado. Nos casos C01-CT01, C01-CT02, C02-CT01, C04-CT04, C04-CT10, C06-CT07 e C09-CT03, uma execução passou e outra encontrou a falha; o caso conta como falhou.

Evidências: 95 casos têm vídeo ou print, e 126 aguardam o vídeo (marcados com `[Vídeo](coloque o link do video aqui)`). Dos 105 bugs, 54 têm vídeo ou print, e 51 aguardam o vídeo (`[BUG:NN](coloque o link do video aqui)`). O roteiro está em `5-Roteiro-de-videos.md`.

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                          | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s)                                                                                        |
| --------- | ------------------------------- | -------------- | -------------- | ---------------- | ---------------------------------------------------------------------------------------------------------- |
| RF01      | Login na plataforma             | 9              | 2              | 8                | BUG-001, BUG-002, BUG-003, BUG-004, BUG-005, BUG-006, BUG-007, BUG-011                                     |
| RF02      | Página inicial do dashboard     | 10             | 3              | 9                | BUG-007, BUG-008, BUG-009, BUG-010, BUG-014, BUG-015, BUG-034, BUG-035, BUG-100                            |
| RF03      | Dashboard                       | 4              | 1              | 3                | BUG-012, BUG-013, BUG-014                                                                                  |
| RF04      | Gestão de clientes              | 16             | 4              | 12               | BUG-016, BUG-017, BUG-036, BUG-037, BUG-038, BUG-039, BUG-040, BUG-041, BUG-101, BUG-102, BUG-103, BUG-104 |
| RF05      | Gestão de planos                | 14             | 8              | 6                | BUG-042, BUG-043, BUG-044, BUG-045, BUG-046, BUG-047 (em revisão: BUG-025)                                 |
| RF06      | Gestão de matrículas            | 14             | 4              | 9                | BUG-018, BUG-048, BUG-049, BUG-050, BUG-051, BUG-052, BUG-053, BUG-054, BUG-105                            |
| RF07      | Contas a receber                | 13             | 8              | 5                | BUG-019, BUG-055, BUG-056, BUG-057, BUG-058                                                                |
| RF08      | Gestão de fornecedores          | 9              | 6              | 3                | BUG-059, BUG-060, BUG-061                                                                                  |
| RF09      | Check-in e presenças            | 12             | 4              | 7                | BUG-022, BUG-023, BUG-062, BUG-063, BUG-064, BUG-065, BUG-066                                              |
| RF10      | Avaliações físicas              | 11             | 7              | 4                | BUG-067, BUG-068, BUG-069, BUG-070                                                                         |
| RF11      | Turmas e SifitBox               | 13             | 10             | 3                | BUG-071, BUG-072, BUG-073                                                                                  |
| RF12      | Caixas                          | 11             | 5              | 6                | BUG-021, BUG-074, BUG-075, BUG-076, BUG-077, BUG-078                                                       |
| RF13      | Contas a pagar e despesas fixas | 16             | 10             | 6                | BUG-020, BUG-079, BUG-080, BUG-081, BUG-082, BUG-083                                                       |
| RF14      | Fichas de treino e exercícios   | 13             | 8              | 4                | BUG-084, BUG-085, BUG-086, BUG-087                                                                         |
| RF15      | Prospecção                      | 12             | 11             | 1                | BUG-088 (em revisão: BUG-026)                                                                              |
| RF16      | Colaboradores e funções         | 17             | 11             | 5                | BUG-024, BUG-089, BUG-090, BUG-091, BUG-092 (em revisão: BUG-027)                                          |
| RF17      | Produtos                        | 11             | 7              | 4                | BUG-028, BUG-093, BUG-094, BUG-095                                                                         |
| RF18      | Fichas de anamnese              | 7              | 3              | 4                | BUG-096, BUG-097, BUG-098, BUG-099                                                                         |
| RF19      | Cadastros de apoio              | 9              | 4              | 5                | BUG-029, BUG-030, BUG-031, BUG-032, BUG-033                                                                |

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
| BUG-015 | Card de avaliações pendentes mostra 0, mas a lista tem pendentes                    | Alta       | Aberto     |
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
| BUG-027 | Cadastro de Funções não avisa nada ao salvar vazio                                  | Média      | Em revisão |
| BUG-028 | Erro genérico ao salvar produto vazio                                               | Baixa      | Aberto     |
| BUG-029 | Erro genérico ao salvar enquete vazia                                               | Baixa      | Aberto     |
| BUG-030 | Atividades permite salvar registro em branco                                        | Média      | Aberto     |
| BUG-031 | Objetivos de Treino permite salvar registro em branco                               | Média      | Aberto     |
| BUG-032 | Tipos de Pagamento permite salvar registro em branco                                | Média      | Aberto     |
| BUG-033 | Erro ao salvar pergunta de anamnese vazia                                           | Média      | Aberto     |
| BUG-034 | Quantidade de clientes ausentes diverge entre a Página Inicial e a tela de Clientes | Média      | Aberto     |
| BUG-035 | Lista de desistências vazia, embora o total informe 3 desistências                  | Média      | Aberto     |
| BUG-036 | Erro ao cadastrar cliente com dados válidos                                         | Crítica    | Aberto     |
| BUG-037 | Busca por código não retorna clientes sem matrícula                                 | Média      | Aberto     |
| BUG-038 | Listagem não respeita a quantidade de registros por página                          | Baixa      | Aberto     |
| BUG-039 | Ausência de mensagem quando a busca não encontra clientes                           | Baixa      | Aberto     |
| BUG-040 | Erro ao salvar alterações dos dados do cliente                                      | Crítica    | Aberto     |
| BUG-041 | Erro no servidor ao acessar cliente excluído                                        | Baixa      | Aberto     |
| BUG-042 | Coluna "Alunos", ranking e receita estimada dos planos exibem valores zerados       | Média      | Aberto     |
| BUG-043 | Busca por código retorna planos cujo código apenas contém o valor informado         | Baixa      | Aberto     |
| BUG-044 | Erro interno com exposição de SQL ao salvar plano sem grupo                         | Média      | Aberto     |
| BUG-045 | Sistema permite cadastrar plano com quantidade de parcelas negativa                 | Média      | Aberto     |
| BUG-046 | Inativação do plano não é salva                                                     | Alta       | Aberto     |
| BUG-047 | Planos inativos são exibidos no cadastro de matrícula                               | Média      | Aberto     |
| BUG-048 | Desconto não é aplicado ao valor total da matrícula                                 | Média      | Aberto     |
| BUG-049 | Mensagem incorreta ao cadastrar matrícula para cliente com matrícula ativa          | Baixa      | Aberto     |
| BUG-050 | Paginação não permite acessar matrículas além da primeira página                    | Média      | Aberto     |
| BUG-051 | Erro no servidor ao excluir matrícula, embora a exclusão seja efetivada             | Média      | Aberto     |
| BUG-052 | Mensagem de validação permanece após selecionar o tipo de pagamento                 | Baixa      | Aberto     |
| BUG-053 | Ausência de mensagem quando a busca não encontra matrículas                         | Baixa      | Aberto     |
| BUG-054 | Campo "Dia Vencimento" aceita data e exibe erro de SQL ao salvar a matrícula        | Média      | Aberto     |
| BUG-055 | Indicador "Contas Atrasadas" diverge do filtro de contas vencidas                   | Média      | Aberto     |
| BUG-056 | Recebimento é registrado sem tipo de pagamento                                      | Média      | Aberto     |
| BUG-057 | Recebimento aceita valor maior que o valor a receber sem alerta                     | Baixa      | Aberto     |
| BUG-058 | Ausência de mensagem quando a busca não encontra contas a receber                   | Baixa      | Aberto     |
| BUG-059 | Busca por código inexistente exibe erro no servidor e mantém todos os fornecedores  | Baixa      | Aberto     |
| BUG-060 | Erro ao cadastrar fornecedor com dados válidos                                      | Alta       | Aberto     |
| BUG-061 | Erro interno com exposição de SQL ao alterar fornecedor                             | Alta       | Aberto     |
| BUG-062 | Check-ins realizados não aparecem na tela de Presenças                              | Alta       | Aberto     |
| BUG-063 | Check-in permanece "Pendente" e não há retorno ao registrar entrada novamente       | Média      | Aberto     |
| BUG-064 | Horário de entrada do check-in exibido com 3 horas a mais                           | Média      | Aberto     |
| BUG-065 | Cliente sem matrícula ativa é liberado para check-in                                | Alta       | Aberto     |
| BUG-066 | Ausência de mensagens no check-in manual e na entrada rápida                        | Baixa      | Aberto     |
| BUG-067 | Erro ao salvar avaliação realizada                                                  | Alta       | Aberto     |
| BUG-068 | Alteração de data e hora da avaliação não é salva                                   | Média      | Aberto     |
| BUG-069 | Cadastro de avaliação aceita hora inválida e retorna erro interno                   | Baixa      | Aberto     |
| BUG-070 | IMC exibido sem formatação                                                          | Baixa      | Aberto     |
| BUG-071 | Erro ao salvar alterações da turma                                                  | Alta       | Aberto     |
| BUG-072 | Cadastro de turma aceita hora final anterior à hora inicial                         | Média      | Aberto     |
| BUG-073 | "Gerar aulas" do SifitBox não informa o resultado                                   | Baixa      | Aberto     |
| BUG-074 | Fechamento de caixa não é salvo após "Buscar Contas"                                | Alta       | Aberto     |
| BUG-075 | Caixa pode ser fechado sem a conferência das contas                                 | Média      | Aberto     |
| BUG-076 | Sistema permite abrir mais de um caixa no mesmo local                               | Média      | Aberto     |
| BUG-077 | Indicador "Caixas Fechados" é reduzido ao abrir um caixa                            | Baixa      | Aberto     |
| BUG-078 | Listagem inicial de caixas ignora o período exibido no filtro                       | Baixa      | Aberto     |
| BUG-079 | Não é possível registrar o pagamento de conta a pagar                               | Alta       | Aberto     |
| BUG-080 | Indicadores "Total a Pagar" e "Valor Restante" exibem zero                          | Média      | Aberto     |
| BUG-081 | Erro no servidor exibido após excluir conta a pagar                                 | Baixa      | Aberto     |
| BUG-082 | Visualização da conta a pagar exibe códigos internos e campos vazios                | Baixa      | Aberto     |
| BUG-083 | Despesa fixa aceita valor negativo e erro interno com valor em texto                | Média      | Aberto     |
| BUG-084 | Ficha de treino não pode ser aberta nem salva                                       | Alta       | Aberto     |
| BUG-085 | Mensagem genérica ao criar ficha sem objetivo do treino                             | Média      | Aberto     |
| BUG-086 | Exclusão de ficha de treino expõe comandos SQL                                      | Média      | Aberto     |
| BUG-087 | Sistema permite cadastrar exercício duplicado no mesmo grupo                        | Baixa      | Aberto     |
| BUG-088 | Sistema permite cadastrar lead duplicado                                            | Baixa      | Aberto     |
| BUG-089 | Busca de colaborador por código inexistente exibe linha vazia                       | Baixa      | Aberto     |
| BUG-090 | Alteração de colaborador expõe comandos SQL                                         | Média      | Aberto     |
| BUG-091 | Funções não podem ser alteradas nem excluídas                                       | Média      | Aberto     |
| BUG-092 | Sistema permite cadastrar função duplicada                                          | Baixa      | Aberto     |
| BUG-093 | Produto do tipo Pontuação não pode ser cadastrado                                   | Alta       | Aberto     |
| BUG-094 | Sistema permite cadastrar produto com preço negativo                                | Média      | Aberto     |
| BUG-095 | Valores dos produtos exibidos sem formatação monetária                              | Baixa      | Aberto     |
| BUG-096 | Anamneses aplicadas não aparecem na listagem                                        | Alta       | Aberto     |
| BUG-097 | Perguntas do modelo de anamnese não são exibidas                                    | Alta       | Aberto     |
| BUG-098 | Assistente de anamnese avança sem aluno e falha com erro interno                    | Média      | Aberto     |
| BUG-099 | Nome do aluno não é exibido na escolha do modelo de anamnese                        | Baixa      | Aberto     |
| BUG-100 | Filtro de período aceita data inicial maior que a final                             | Baixa      | Aberto     |
| BUG-101 | Cadastro de cliente aceita data de nascimento futura                                | Média      | Aberto     |
| BUG-102 | CPF inválido é aceito no cadastro de cliente                                        | Média      | Aberto     |
| BUG-103 | Filtro de status "Ativo" lista clientes inativos                                    | Média      | Aberto     |
| BUG-104 | Ficha do cliente exibe "null" e objetivos fictícios                                 | Baixa      | Aberto     |
| BUG-105 | Campo "Data" da parcela aceita data inválida                                        | Média      | Aberto     |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

- Passaram: 116
- Falharam: 105

**Severidade dos bugs abertos:**

- Crítica: 2
- Alta: 22
- Média: 46
- Baixa: 32

**Em revisão:** 3

---

## 🔍 **Identificação da Causa Raiz (Root Cause Analysis)**

As hipóteses abaixo foram levantadas a partir do comportamento na tela, do console do navegador e das respostas da API (DevTools). São hipóteses, não confirmações do código do sistema.

- **BUG-014, BUG-034, BUG-035**: cada tela calcula os indicadores com regras ou consultas diferentes (ex.: "ausente" na Página Inicial considera quem nunca visitou, e a tela de Clientes não), o que indica a ausência de uma regra única de cálculo.
- **BUG-013**: o console do navegador registra o erro "Invalid scale configuration for scale: yAxes", indicando configuração desatualizada da biblioteca de gráficos, e as cores dos títulos não foram ajustadas ao tema dos cartões.
- **BUG-036, BUG-040**: as rotas de cadastro e de atualização de cliente retornam erro 500 ("Erro interno inesperado.") mesmo com dados válidos, o que indica uma falha comum no back-end, como erro de persistência no banco de dados ou de tratamento dos campos enviados.
- **BUG-037**: a busca por código funciona apenas para clientes com matrícula. A hipótese foi confirmada durante os testes de matrículas: após matricular a cliente 408, ela passou a ser encontrada pela busca por código, o que indica que a consulta depende do vínculo com a matrícula.
- **BUG-016, BUG-038**: a quantidade de páginas parece ser calculada sobre o total de clientes, sem considerar o filtro aplicado, e o limite por página não é aplicado no primeiro carregamento.
- **BUG-041**: o sistema não trata o caso de cliente inexistente e retorna erro 500 em vez de uma mensagem de "cliente não encontrado".
- **BUG-044, BUG-045**: o back-end não valida os campos do plano antes de gravar no banco de dados; o erro de restrição do banco é devolvido diretamente na resposta da API.
- **BUG-046**: o status "inativo" é enviado corretamente pela tela, mas não é gravado, o que indica que a rota de atualização ignora o campo de status.
- **BUG-048**: o campo "Desconto" exibido na visualização recebe o valor da parcela, o que sugere que o campo errado é gravado ou lido, e o valor total não é recalculado na tela de cadastro.
- **BUG-049, BUG-051**: a API retorna o motivo correto ("Já existe matrícula ativa") ou realiza a operação, mas a tela exibe uma mensagem genérica de erro, indicando falha no tratamento das respostas da API.
- **BUG-050**: a quantidade de páginas não é calculada a partir do total de matrículas, impedindo a navegação além da primeira página.
- **BUG-056, BUG-057**: o formulário de recebimento não valida os campos antes do envio e o back-end aceita os dados sem validação.
- **BUG-060, BUG-061**: a atualização do fornecedor não envia o campo "tipo_pessoa" (Física/Jurídica), que é obrigatório no banco de dados; o mesmo padrão de erro 500 no cadastro e na alteração ocorre em Clientes (BUG-036 e BUG-040), o que sugere uma falha comum nas rotas de gravação de cadastros.
- **BUG-062, BUG-063, BUG-064, BUG-065**: o check-in é gravado em uma tabela própria (a API retorna o código do check-in), mas não gera o registro de presença nem atualiza o status; o horário é armazenado em UTC e exibido sem conversão para o fuso de Brasília; a liberação do check-in não consulta a situação da matrícula do cliente.
- **BUG-067, BUG-068, BUG-069**: a rota de registro da avaliação retorna erro 500 mesmo com dados válidos, o botão "Salvar" da alteração de data e hora não dispara nenhuma requisição e os campos de hora não são validados na tela antes do envio.
- **BUG-071, BUG-072**: a rota de atualização de turma retorna erro 500 mesmo sem alterações, o que indica falha no back-end independente dos dados enviados; o horário não é validado nem na tela nem no back-end.
- **BUG-021, BUG-074, BUG-075, BUG-076, BUG-077**: o fluxo de fechamento não valida se as contas foram conferidas e deixa de enviar o fechamento após a busca das contas; a abertura não verifica se já existe caixa aberto para o local nem valida o local antes do envio; o indicador de caixas fechados é calculado sobre um total fixo, e não sobre a quantidade real de caixas.
- **BUG-020, BUG-079, BUG-080, BUG-081, BUG-082, BUG-083**: a tela de contas a pagar não implementa a ação de pagamento nem calcula os indicadores de valores; os formulários de contas a pagar e despesas fixas não validam os campos na tela e o back-end aceita valores negativos ou devolve erro 500 para dados inválidos.
- **BUG-084, BUG-086**: o banco de dados de homologação não possui a coluna "descanso_padrao" utilizada pela consulta da ficha, o que indica migração de banco não aplicada no ambiente; a rota de exclusão devolve a saída de depuração do SQL na resposta.
- **BUG-024**: os campos de seleção exibem a primeira opção visualmente, mas o valor vinculado ao formulário permanece vazio, e o back-end não valida esses campos antes de gravar; o mesmo padrão de erro 500 em cadastros ocorre em Clientes (BUG-036) e Fornecedores (BUG-060).
- **BUG-086, BUG-090**: as rotas de exclusão de ficha e de atualização de colaborador devolvem a saída de depuração do SQL, o que indica modo de depuração ativo no back-end de homologação.
- **BUG-028, BUG-093**: o back-end grava o campo "valor" mesmo para produtos de pontuação e não trata o valor vazio, devolvendo o erro do banco de dados ("Data truncated for column 'valor'") na resposta.
- **BUG-096, BUG-097, BUG-098**: a listagem consulta as fichas com o parâmetro "id" nulo; o assistente não carrega as perguntas do modelo e não valida o aluno antes de avançar, enviando a anamnese sem respostas ou sem aluno.

| Grupo de bugs                                                 | Causa raiz provável                                                                                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| BUG-004, BUG-044, BUG-066, BUG-087, BUG-101, BUG-102, BUG-105 | Validações ausentes ou parciais no front-end e sem regra no back-end (dados inválidos chegam ao banco; campo faltante gera HTTP 500) |
| BUG-016, BUG-103                                              | Filtros não enviados na listagem inicial e na troca de página                                                                        |
| BUG-010, BUG-019, BUG-063                                     | Indicadores calculados com consulta diferente da usada nas listagens                                                                 |
| BUG-064                                                       | Data e hora gravadas em UTC sem conversão para America/Sao_Paulo                                                                     |
| BUG-104                                                       | Componentes da ficha com valores fixos (mock) e campos nulos exibidos como "null"                                                    |
| BUG-002, BUG-047, BUG-100                                     | Regras de negócio não implementadas (recuperação de senha, filtro de plano ativo, validação de período)                              |

No banco (MySQL Workbench, somente leitura), o cliente de teste aparece gravado. A coluna `cpf` da tabela `pessoas` é guardada criptografada, por isso a validação do CPF inválido (BUG-102) foi feita pela tela de edição.

---

## 📁 **Evidências e Documentos**

- Plano de Testes
- Análise de requisitos
- Casos de teste (C01 a C19); os casos sem vídeo estão marcados com `[Vídeo](coloque o link do video aqui)`. Os cenários com algum caso sem vídeo estão na pasta `Cenarios de testes/Pendentes de evidencias` (C02, C04, C06 e C09 a C19)
- Relatório de bugs, com o vídeo da falha
- Vídeos no Jam e prints na pasta `Sifit/Evidencias`
- Roteiro dos vídeos a gravar (`5-Roteiro-de-videos.md`)

---

## ✅ **Conclusão**

Dos 221 casos, 116 passaram e 105 falharam, com 105 bugs registrados: 102 abertos e 3 em revisão. No login, só o usuário inexistente e o logout passaram: o login válido mostra erro no servidor ou entra mostrando o nome Jair, a senha incorreta já mostrou erro no servidor, os campos vazios seguem para a API sem aviso, os espaços nas pontas derrubam o login, o link "Esqueci minha senha" não faz nada e a sessão não é controlada.

As falhas mais graves impedem o uso de módulos centrais. Não é possível cadastrar nem alterar clientes (BUG-036 e BUG-040, severidade Crítica) e fornecedores (BUG-060 e BUG-061). A inativação do plano não é salva (BUG-046). O fechamento de caixa com conferência não é gravado (BUG-074). Não há como registrar o pagamento de conta a pagar (BUG-079). A ficha de treino não abre nem salva (BUG-084). A avaliação realizada não é salva (BUG-067). As anamneses aplicadas não aparecem (BUG-096 e BUG-097). Também se repetem formulários vazios que geram erro 500, respostas da API que expõem comandos SQL, registros em branco aceitos (Atividades, Objetivos de Treino e Tipos de Pagamento) e números que mudam de uma tela para outra (alunos em risco, avaliações pendentes, check-ins do dia, matrículas ativas contra clientes ativos e totais de contas a receber).

Funcionam bem a prospecção (11 de 12 casos), as turmas (10 de 13) e a validação do campo obrigatório em Clientes, Matrículas, Avaliações, Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios e Categorias Crossfit.

Ficaram fora do escopo: Pagar.me, WhatsApp e Aplicativo. Ainda não têm caso de teste: Grupos, Modelos de contrato, Box - Turmas, Grupos musculares, Modelos de ficha, Configurações, Relatórios, Importar avaliações, Inteligência & Automação, Resultados IA, Local de contas, Bancos, Banco recorrente, Categorias de conta a pagar, Métricas do cliente e Modelos e categorias de anamnese (RF20 a RF33 no plano). O teste de formulário vazio criou 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12), que devem ser excluídos.

Até 23/10/2026 os testes usaram https://sifit.centrion.com.br/. A partir de 24/10/2026, usam https://sifitalfa.centrion.com.br/. A versão interna do sistema não foi anotada.
