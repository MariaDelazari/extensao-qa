## 🧪 **Plano de Testes - Sifit Centrion**

### 📌 1. **Identificação**

- **Nome do Projeto**: Sifit Centrion (SIFIT - Sistema para Academias)
- **Versão Avaliada**: Sifit Centrion e Sifit Unialfa. A versão interna do sistema não foi anotada.
- **Ambiente de Testes**: https://sifit.centrion.com.br/ até 23/10/2026. Em 24/10/2026, o professor pediu para continuar os testes em https://sifitalfa.centrion.com.br/
- **Tipo de Teste**: Teste funcional manual
- **Data do Documento**: 12/10/2026. Versão unificada do grupo em 12/11/2026.
- **Responsáveis**: Maria Eduarda Pacheco Delazari, RA: 240017; Ville Nunes Figueiredo da Silva, RA: 14534; Keltton Felipe Alves Silveira, RA: 14509; Daniel Satel Pereira, RA: 14567; Rafael Colombo da Silva, RA: 14551

---

### 🎯 2. **Objetivo**

Verificar manualmente os requisitos funcionais do Sifit: o login, a página inicial, o Dashboard e os módulos de clientes, planos, matrículas, financeiro, presença, avaliações, treinos, prospecção, colaboradores, produtos, anamnese e cadastros de apoio. Os testes conferem o caminho feliz, as validações e mensagens de erro e a coerência dos números entre as telas.

---

### 🧩 3. **Escopo**

**Incluído:**

- RF01 Login: credenciais válidas, senha incorreta, usuário inexistente, campos vazios, espaços nas pontas, "Esqueci minha senha", "Manter conectado", acesso direto a `/dashboard` e logout
- RF02 Página inicial: saudação, cards do resumo, detalhes de cada card, filtro de período e links
- RF03 Dashboard: título, gráficos e indicadores da Inteligência Sifit
- RF04 Clientes: listagem, busca, paginação, cadastro, visualização, alteração e exclusão
- RF05 Planos: listagem, indicadores, busca, cadastro, alteração, inativação e exclusão
- RF06 Matrículas: listagem, busca, paginação, cadastro, desconto, parcelas, cancelamento e exclusão
- RF07 Contas a receber: filtros, totais, cadastro, recebimento e exclusão
- RF08 Fornecedores: busca, cadastro, visualização, alteração e exclusão
- RF09 Check-in e presenças: check-in manual e entrada rápida, indicadores, horário e presenças
- RF10 Avaliações: busca, agendamento, alteração, registro com IMC e exclusão
- RF11 Turmas e SifitBox: cadastro, alteração, exclusão e geração de aulas
- RF12 Caixas: listagem, abertura e fechamento
- RF13 Contas a pagar e despesas fixas: filtros, indicadores, cadastro, pagamento e exclusão
- RF14 Fichas de treino e exercícios: ficha de treino e biblioteca de exercícios
- RF15 Prospecção: busca, cadastro, estágios e exclusão de leads
- RF16 Colaboradores e funções: cadastro, alteração, inativação, funções e permissões
- RF17 Produtos: cadastro de venda e de pontuação, alteração, inativação e exclusão
- RF18 Fichas de anamnese: assistente de aplicação e listagem
- RF19 Cadastros de apoio (9 telas): salvar com o formulário vazio
- RF20 Grupos: busca, filtros, indicadores, cadastro, duplicidade, alteração, inativação e exclusão
- RF21 Modelos de contrato: listagem, cadastro, variáveis do texto e pré-visualização
- RF22 Box - Turmas: modalidades e turmas recorrentes (cadastro, validações, alteração e exclusão)
- RF29 Local Contas: acesso e listagem, cadastro, salvar vazio e cancelar (a tela só abre pelo link)
- RF30 Bancos e Banco recorrente: acesso, listagem, salvar vazio, cadastro, duplicidade, alteração e exclusão (as telas só abrem pelo link)
- RF31 Categorias de conta a pagar: acesso, listagem, salvar vazio, cadastro e duplicidade
- RF32 Métricas do cliente: acesso e busca das métricas e listas do período (a tela só abre pelo link)
- RF33 Modelos e categorias de anamnese: categorias e modelos (busca, indicadores, cadastro, duplicidade, perguntas, preview, alteração, inativação e exclusão)

**Incluído, ainda sem caso de teste (próximos cenários, RF23 a RF28):**

- Grupos musculares (RF23), Modelos de ficha (RF24) e Configurações (RF25)
- Relatórios (RF26), Importar avaliações (RF27) e Inteligência & Automação com Resultados IA (RF28)

**Excluído:**

- Menus, consultas e formulários sem caso de teste
- Integração com a Pagar.me, por envolver cobranças reais
- Envio de mensagens pelo WhatsApp ("Cobrar todos no WhatsApp", "Enviar mensagem"), por enviar mensagens a pessoas reais
- Aplicativo do aluno
- Testes em dispositivos móveis
- Testes de performance, carga e segurança

---

### 🔧 4. **Ferramentas Utilizadas**

- Google Chrome 150.0.7871.46 e 155, no Ubuntu 26.04 LTS, no Linux e no Windows 11
- Ferramentas de inspeção do navegador (DevTools), para analisar envio das requisições e bugs
- Jam, para gravar os vídeos de execução
- Prints, quando o caso não tem vídeo (pasta `Sifit/Evidencias`)
- MySQL Workbench, consulta somente leitura ao banco
- Markdown e Git, para registrar os casos, os bugs e este plano

---

### 🧪 5. **Técnicas de Teste**

- Caminho feliz
- Testes negativos (campos obrigatórios vazios e dados inválidos)
- Particionamento de equivalência (login válido, inválido, vazio e com espaços; CPF válido e inválido; código existente e inexistente)
- Análise de valor limite (data de nascimento futura, valores negativos, período invertido, hora final antes da inicial)
- Teste exploratório no retorno da sessão e no acesso direto pela URL
- Conferência de números entre telas (indicadores contra listas)

---

### 📄 6. **Critérios de Aceitação**

- Cada caso de teste descreve um resultado observável na tela.
- Falha de caso gera um bug com passo a passo e vídeo.
- Mensagem de erro, redirecionamento ou bloqueio precisam ser visíveis para quem repetir o teste.
- Os indicadores devem apresentar os mesmos valores em todas as telas.

---

### 🚦 7. **Critérios de Saída (Exit Criteria)**

- Os casos deste plano foram executados e têm vídeo ou print.
- As falhas encontradas foram registradas no relatório de bugs, com vídeo.
- O relatório final informa quantos casos passaram, quantos falharam e qual bug está ligado a cada um.
- Situação atual: 85 dos 263 casos e 35 dos 122 bugs ainda aguardam o vídeo (ver o relatório final).

---

### ⏱️ 8. **Cronograma Estimado**

| Atividade                   | Data Início | Data Fim   |
| --------------------------- | ----------- | ---------- |
| Planejamento de Testes      | 07/10/2026  | 23/10/2026 |
| Levantamento de requisitos  | 17/10/2026  | 22/10/2026 |
| Criação de Casos de Teste   | 13/10/2026  | 25/10/2026 |
| Execução dos Testes Manuais | 12/10/2026  | 15/11/2026 |
| Registro e Report de Bugs   | 12/10/2026  | 15/11/2026 |
| Unificação dos trabalhos    | 12/11/2026  | 13/11/2026 |
| Encerramento e Evidências   | 12/10/2026  | Pendente   |

Em 24/10/2026, os testes passaram para https://sifitalfa.centrion.com.br/. A data de execução de parte dos módulos RF09 em diante não foi registrada. Os casos da seção 13 foram especificados em 07/10/2026 e ainda não foram executados.

---

### 📋 9. **Módulos a Serem Testados**

| Código RF | Módulo                           | Prioridade |
| --------- | -------------------------------- | ---------- |
| RF01      | Login na plataforma              | Alta       |
| RF02      | Página inicial do dashboard      | Alta       |
| RF03      | Dashboard                        | Média      |
| RF04      | Gestão de clientes               | Alta       |
| RF05      | Gestão de planos                 | Alta       |
| RF06      | Gestão de matrículas             | Alta       |
| RF07      | Contas a receber                 | Alta       |
| RF08      | Gestão de fornecedores           | Baixa      |
| RF09      | Check-in e presenças             | Alta       |
| RF10      | Avaliações físicas               | Média      |
| RF11      | Turmas e SifitBox                | Média      |
| RF12      | Caixas                           | Alta       |
| RF13      | Contas a pagar e despesas fixas  | Alta       |
| RF14      | Fichas de treino e exercícios    | Média      |
| RF15      | Prospecção                       | Média      |
| RF16      | Colaboradores e funções          | Média      |
| RF17      | Produtos                         | Baixa      |
| RF18      | Fichas de anamnese               | Baixa      |
| RF19      | Cadastros de apoio               | Média      |
| RF20      | Grupos                           | Média      |
| RF21      | Modelos de contrato              | Média      |
| RF22      | Box - Turmas                     | Média      |
| RF29      | Local Contas                     | Média      |
| RF30      | Bancos e Banco recorrente        | Média      |
| RF31      | Categorias de conta a pagar      | Baixa      |
| RF32      | Métricas do cliente              | Baixa      |
| RF33      | Modelos e categorias de anamnese | Baixa      |

**Cenário de cada requisito:** o número do RF é o número do cenário e do arquivo. O RF01 é testado em C01 (`CT_RF01_ Login na plataforma.md`), o RF02 em C02, e assim por diante, até o RF33 em C33.

Quando houve diferença de prioridade entre os trabalhos, ficou a maior.

---

### 🐞 10. **Gestão de Defeitos**

- Bugs são documentados em `3-Relatorio-de-Bugs.md` com:
  - Título
  - Descrição
  - Passos para reproduzir
  - Comportamento esperado e comportamento obtido
  - Ambiente
  - Evidência em vídeo
  - Severidade (Crítica, Alta, Média, Baixa)
  - Prioridade de correção e status

---

### 📌 11. **Riscos Identificados**

| Risco                                                                                                                                        | Impacto | Mitigação                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A versão do sistema não foi registrada                                                                                                       | Médio   | Anotar a versão na próxima execução                                                                                                                        |
| O erro no servidor no login inválido esconde a mensagem de credencial incorreta                                                              | Alto    | Conferir a resposta no DevTools além do texto da tela                                                                                                      |
| Os testes de formulário vazio criaram 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12)        | Médio   | Excluir os registros depois de gravar os vídeos dos BUG-029, 030 e 031                                                                                     |
| A sessão se comporta de um jeito no retorno ao sistema e de outro no `/dashboard`                                                            | Alto    | Repetir os dois caminhos no mesmo vídeo, como no BUG-005                                                                                                   |
| Ambiente compartilhado: outros usuários alteram ou excluem dados                                                                             | Alto    | Usar registros de teste identificáveis pelo nome e não fixar IDs na documentação                                                                           |
| Execuções em datas e endereços diferentes deram resultados diferentes (C01-CT01, C01-CT02, C02-CT01, C04-CT04, C04-CT10, C06-CT07, C09-CT03) | Médio   | O resultado de cada execução está descrito no caso e a falha registrada é mantida: se o sistema mudou depois, sem aviso do professor, o caso não é refeito |
| Os casos executados por automação de navegador não mostram o aviso nativo do navegador ("Preencha este campo.")                              | Médio   | Conferido em vídeo: os BUG-025 e BUG-026 foram cancelados (o navegador mostra "Preencha este campo.")                                                      |
| 85 casos e 35 bugs ainda sem vídeo                                                                                                           | Alto    | Gravar os vídeos seguindo o `5-Roteiro-de-videos.md` e os casos que ainda estão sem vídeo                                                                  |
| Ações que enviam mensagens ou cobranças reais (WhatsApp e Pagar.me)                                                                          | Alto    | Manter essas ações fora do escopo                                                                                                                          |
| Dados pessoais reais na base                                                                                                                 | Alto    | Não publicar prints com nome ou CPF de terceiros (LGPD)                                                                                                    |
| Testes limitados a um único usuário (perfil administrador)                                                                                   | Médio   | Documentar esse limite no escopo                                                                                                                           |

---

### 🧾 12. **Dados de Teste Criados no Ambiente**

| Registro criado                                                                  | Caso                          |
| -------------------------------------------------------------------------------- | ----------------------------- |
| Cliente de teste (cadastrado e depois editado)                                   | C04-CT12 e C04-CT10           |
| Exercício de teste no grupo Peitoral                                             | C14-CT10                      |
| Plano de teste                                                                   | C05-CT07                      |
| Matrícula do cliente de teste no plano de teste                                  | C06-CT07                      |
| Parcela gerada pela matrícula                                                    | C07-CT12                      |
| Check-in do cliente de teste                                                     | C09-CT03                      |
| Registros identificados pelo nome (por exemplo, "Produto Teste Ville")           | Vários cenários               |
| Registros em branco: Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12 | C19-CT04, C19-CT07 e C19-CT08 |
| Grupos #8, #9 e #10 (não podem ser excluídos, BUG-105)                           | C20-CT05, C20-CT07 e C20-CT09 |
| Modelos de contrato 8 e 9 (não aparecem na listagem, BUG-106)                    | C21-CT03 e C21-CT06           |
| Bancos 8 a 17 (a exclusão de banco não é segura, BUG-129)                        | C30-CT03 a C30-CT06           |
| Categorias de conta a pagar 25 a 29 (não aparecem na listagem, BUG-130)          | C31-CT03 a C31-CT05           |

Os códigos dos registros não ficam fixos neste documento, porque o ambiente é compartilhado e os dados são alterados por outras pessoas.

---

### 🧾 13. **Casos especificados e ainda não executados**

Estes casos foram escritos, mas não foram executados, e não têm vídeo nem resultado. Por isso não entram nos cenários nem na conta do relatório final. Para entrar, cada um precisa ser executado, gravado e receber o próximo ID do cenário.

| Caso proposto                                          | Requisito | Situação      |
| :----------------------------------------------------- | :-------- | :------------ |
| Prevenção de duplo clique no botão Entrar              | RF01      | Não executado |
| Data de término anterior à data de início na matrícula | RF06      | Não executado |

---

### 📁 14. **Entregáveis**

- Plano de Testes
- Análise de requisitos
- Casos de teste (C01 a C22, C30 e C31); os casos sem vídeo estão marcados com `[Vídeo](coloque o link do video aqui)`. Os cenários com algum caso sem vídeo ficam em `Cenarios de testes/Pendentes de evidencias`
- Roteiro dos vídeos a gravar (`5-Roteiro-de-videos.md`)
- Relatório de bugs com vídeos
- Relatório final de execução
- Prints de evidência (`Sifit/Evidencias`)
