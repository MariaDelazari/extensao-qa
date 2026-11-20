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
- RF23 Grupos musculares: busca, filtro por tipo de membro, paginação, cadastro, validações, duplicidade, alteração e exclusão
- RF24 Modelos de ficha: busca pelo criador e pelo código, criação, alteração e exclusão
- RF25 Configurações: abas, cancelar, salvar, validação de valores e ocultação de senhas e tokens
- RF26 Relatórios: acesso, 7 modelos, filtros dinâmicos, geração de PDF, datas vazias, período invertido, período sem registros e limite de ano
- RF27 Importar avaliações: acesso, navegação, contraste no modo escuro, instruções/planilha modelo, envio fora do padrão e rejeição de extensão inválida (`.pdf`)
- RF28 Inteligência & Automação e Resultados IA: filtros de período, coerência de indicadores, atividade recente, modais de configuração, resultados de risco, consultas de leitura e prévia de cobranças (sem disparar envios reais)
- RF29 Local Contas: acesso e listagem, cadastro, salvar vazio e cancelar (a tela só abre pelo link)
- RF30 Bancos e Banco recorrente: acesso, listagem, salvar vazio, cadastro, duplicidade, alteração e exclusão (as telas só abrem pelo link)
- RF31 Categorias de conta a pagar: acesso, listagem, salvar vazio, cadastro e duplicidade
- RF32 Métricas do cliente: acesso e busca das métricas e listas do período (a tela só abre pelo link)
- RF33 Modelos e categorias de anamnese: categorias e modelos (busca, indicadores, cadastro, duplicidade, perguntas, preview, alteração, inativação e exclusão)

**Excluído:**

- Menus, consultas e formulários sem caso de teste
- Integração com a Pagar.me, por envolver cobranças reais
- Envio de mensagens pelo WhatsApp ("Cobrar todos no WhatsApp", "Enviar mensagem"), por enviar mensagens a pessoas reais
- Aplicativo do aluno
- Testes em dispositivos móveis
- Testes de performance, carga e segurança

---

### 🔧 4. **Ferramentas Utilizadas**

- Google Chrome 150.0.7871.46, 155 e 157, no Ubuntu 26.04 LTS, no Linux Mint e no Windows 11
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
- Situação atual: todos os 350 casos (C01 a C33) e todos os 165 bugs abertos têm evidência em vídeo ou print (ver o relatório final).

---

### ⏱️ 8. **Cronograma Estimado**

| Atividade                   | Data Início | Data Fim   |
| --------------------------- | ----------- | ---------- |
| Planejamento de Testes      | 07/10/2026  | 23/10/2026 |
| Levantamento de requisitos  | 17/10/2026  | 22/10/2026 |
| Criação de Casos de Teste   | 13/10/2026  | 19/11/2026 |
| Execução dos Testes Manuais | 12/10/2026  | 19/11/2026 |
| Registro e Report de Bugs   | 12/10/2026  | 19/11/2026 |
| Unificação dos trabalhos    | 12/11/2026  | 19/11/2026 |
| Encerramento e Evidências   | 12/10/2026  | 19/11/2026 |

Em 24/10/2026, os testes passaram para https://sifitalfa.centrion.com.br/. Em 19/11/2026, foram concluídas as gravações de RF10, RF13, os casos extras da seção 13 (C01-CT10 e C06-CT15) e os módulos novos RF26, RF27 e RF28.

---

### 📋 9. **Módulos a Serem Testados**

| Código RF | Módulo                                   | Prioridade |
| --------- | ---------------------------------------- | ---------- |
| RF01      | Login na plataforma                      | Alta       |
| RF02      | Página inicial do dashboard              | Alta       |
| RF03      | Dashboard                                | Média      |
| RF04      | Gestão de clientes                       | Alta       |
| RF05      | Gestão de planos                         | Alta       |
| RF06      | Gestão de matrículas                     | Alta       |
| RF07      | Contas a receber                         | Alta       |
| RF08      | Gestão de fornecedores                   | Baixa      |
| RF09      | Check-in e presenças                     | Alta       |
| RF10      | Avaliações físicas                       | Média      |
| RF11      | Turmas e SifitBox                        | Média      |
| RF12      | Caixas                                   | Alta       |
| RF13      | Contas a pagar e despesas fixas          | Alta       |
| RF14      | Fichas de treino e exercícios            | Média      |
| RF15      | Prospecção                               | Média      |
| RF16      | Colaboradores e funções                  | Média      |
| RF17      | Produtos                                 | Baixa      |
| RF18      | Fichas de anamnese                       | Baixa      |
| RF19      | Cadastros de apoio                       | Média      |
| RF20      | Grupos                                   | Média      |
| RF21      | Modelos de contrato                      | Média      |
| RF22      | Box - Turmas                             | Média      |
| RF23      | Grupos musculares                        | Média      |
| RF24      | Modelos de ficha                         | Média      |
| RF25      | Configurações                            | Média      |
| RF26      | Relatórios                               | Alta       |
| RF27      | Importar avaliações                      | Média      |
| RF28      | Inteligência & Automação e Resultados IA | Alta       |
| RF29      | Local Contas                             | Média      |
| RF30      | Bancos e Banco recorrente                | Média      |
| RF31      | Categorias de conta a pagar              | Baixa      |
| RF32      | Métricas do cliente                      | Baixa      |
| RF33      | Modelos e categorias de anamnese         | Baixa      |

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

| Risco                                                                                                                                        | Impacto | Mitigação                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A versão do sistema não foi registrada                                                                                                       | Médio   | Anotar a versão na próxima execução                                                                                                                                           |
| O erro no servidor no login inválido esconde a mensagem de credencial incorreta                                                              | Alto    | Conferir a resposta no DevTools além do texto da tela                                                                                                                         |
| Os testes de formulário vazio criaram 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12)        | Médio   | Excluir os registros depois de gravar os vídeos dos BUG-029, 030 e 031                                                                                                        |
| A sessão se comporta de um jeito no retorno ao sistema e de outro no `/dashboard`                                                            | Alto    | Repetir os dois caminhos no mesmo vídeo, como no BUG-005                                                                                                                      |
| Ambiente compartilhado: outros usuários alteram ou excluem dados                                                                             | Alto    | Usar registros de teste identificáveis pelo nome e não fixar IDs na documentação                                                                                              |
| Execuções em datas e endereços diferentes deram resultados diferentes (C01-CT01, C01-CT02, C02-CT01, C04-CT04, C04-CT10, C06-CT07, C09-CT03) | Médio   | O resultado de cada execução está descrito no caso e a falha registrada é mantida: se o sistema mudou depois, sem aviso do professor, o caso não é refeito                    |
| Os casos executados por automação de navegador não mostram o aviso nativo do navegador ("Preencha este campo.")                              | Médio   | Conferido em vídeo: os BUG-025 e BUG-026 foram cancelados (o navegador mostra "Preencha este campo.") e o BUG-122 também (o vídeo do C25-CT04 mostra a confirmação ao salvar) |
| 6 casos com print em vez de vídeo (C05-CT13, C05-CT14, C09-CT05, C09-CT07, C09-CT08 e C14-CT09)                                              | Baixo   | O print foi aceito como evidência; todos os outros casos e todos os bugs abertos têm vídeo                                                                                    |
| Ações que enviam mensagens ou cobranças reais (WhatsApp e Pagar.me)                                                                          | Alto    | Manter essas ações fora do escopo                                                                                                                                             |
| Dados pessoais reais na base                                                                                                                 | Alto    | Não publicar prints com nome ou CPF de terceiros (LGPD)                                                                                                                       |
| Testes limitados a um único usuário (perfil administrador)                                                                                   | Médio   | Documentar esse limite no escopo                                                                                                                                              |

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

### 🧾 13. **Casos especificados posteriormente executados**

Estes casos foram especificados inicialmente em 07/10/2026 e executados em 19/11/2026 com evidência em vídeo, sendo incorporados aos respectivos cenários.

| Caso proposto                                          | Requisito | Situação                                      |
| :----------------------------------------------------- | :-------- | :-------------------------------------------- |
| Prevenção de duplo clique no botão Entrar              | RF01      | Executado em 19/11/2026 (C01-CT10 e C01-CT11) |
| Data de término anterior à data de início na matrícula | RF06      | Executado em 19/11/2026 (C06-CT15)            |

---

### 📁 14. **Entregáveis**

- Plano de Testes
- Análise de requisitos
- Casos de teste (C01 a C33), todos com evidência: vídeo no Jam ou print em `Sifit/Evidencias`. A pasta `Cenarios de testes/Pendentes de evidencias` ficou vazia
- Relatório de bugs com vídeo (o BUG-062 tem print)
- Relatório final de execução
- Prints de evidência (`Sifit/Evidencias`)
