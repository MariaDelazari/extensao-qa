## 🧪 **Plano de Testes - Sifit Centrion**

### 📌 1. **Identificação**

- **Nome do Projeto**: Sifit Centrion
- **Versão Avaliada**: Sifit Centrion e Sifit Unialfa
- **Ambiente de Testes**: Sifit Centrion. Em 24/10/2026, o professor pediu para continuar os testes em https://sifitalfa.centrion.com.br/
- **Tipo de Teste**: Teste funcional manual
- **Data do Documento**: 12/10/2026
- **Responsável**: Maria Eduarda Pacheco Delazari

---

### 🎯 2. **Objetivo**

Verificar o login do Sifit Centrion: acesso com credenciais válidas, rejeição de credenciais inválidas, campos obrigatórios, espaços nas pontas dos campos, recuperação de senha e controle da sessão.

---

### 🧩 3. **Escopo**

**Incluído:**

- Login com credenciais válidas
- Login com senha incorreta
- Campos obrigatórios vazios
- Espaços no início ou no fim das credenciais
- Link "Esqueci minha senha"
- Opção "Manter conectado"
- Acesso direto ao endereço `/dashboard`
- Página inicial: saudação, cards do resumo e avaliações pendentes
- Dashboard: título, gráficos e indicadores da Inteligência Sifit
- Clientes: listagem, paginação, busca por nome e por código, cadastro com campos vazios
- Matrículas: listagem, cadastro sem cliente e coerência com os clientes ativos
- Contas a receber: totais e valores da listagem
- Contas a pagar, Caixas e Colaboradores: salvar com os campos vazios
- Check-in: indicadores, lista e horário de pico
- Avaliações: cadastro sem aluno
- Cadastros de apoio (16 telas): salvar com o formulário vazio

**Excluído:**

- Menus, consultas e formulários depois do login que ficaram sem vídeo
- Cadastro completo com dados válidos, edição e exclusão de registros nas telas novas (não executados, para não alterar os dados do ambiente compartilhado)
- Pagar.me, Inteligência & Automação, Resultados IA, Relatórios, Configurações, Aplicativo, Fichas de Treino, Modelos de Contrato e Anamnese (telas abertas sem erro, mas sem caso de teste)
- Testes em dispositivos móveis
- Testes de performance ou carga

---

### 🔧 4. **Ferramentas Utilizadas**

- Google Chrome 150.0.7871.46
- Ferramentas de inspeção do navegador (DevTools), para analisar envio das requisições e bugs
- Jam, para gravar os vídeos de execução
- Markdown e Git, para registrar os casos, os bugs e este plano

---

### 🧪 5. **Técnicas de Teste**

- Caminho feliz
- Testes negativos
- Particionamento de equivalência nos dados de login (válido, inválido, vazio e com espaços)
- Teste exploratório no retorno da sessão e no acesso direto pela URL
- Validação de formulário vazio e conferência de números entre telas (indicadores contra listas)

---

### 📄 6. **Critérios de Aceitação**

- Cada caso de teste descreve um resultado observável na tela.
- Falha de caso gera um bug com passo a passo e vídeo.
- Mensagem de erro, redirecionamento ou bloqueio precisam ser visíveis para quem repetir o teste.

---

### 🚦 7. **Critérios de Saída (Exit Criteria)**

- Os casos de login deste plano foram executados.
- As falhas encontradas foram registradas no relatório de bugs, com vídeo.
- O relatório final informa quantos casos passaram, quantos falharam e qual bug está ligado a cada um.

---

### ⏱️ 8. **Cronograma Estimado**

| Atividade                   | Data Início    | Data Fim       |
| --------------------------- | -------------- | -------------- |
| Planejamento de Testes      | não registrado | não registrado |
| Criação de Casos de Teste   | não registrado | não registrado |
| Execução dos Testes Manuais | 12/10/2026     | 28/10/2026     |
| Registro e Report de Bugs   | 12/10/2026     | 28/10/2026     |
| Encerramento e Evidências   | 12/10/2026     | Pendente (vídeos) |

A execução registrada no relatório de bugs começa em 12/10/2026. Em 24/10/2026, os testes passaram para https://sifitalfa.centrion.com.br/. As datas de planejamento e de escrita dos casos não foram anotadas. Os cenários C03 a C12 foram executados em 28/10/2026 e aguardam os vídeos.

---

### 📋 9. **Módulos a Serem Testados**

| Código RF | Módulo                             | Prioridade |
| --------- | ---------------------------------- | ---------- |
| RF01      | Login com credenciais válidas      | Alta       |
| RF02      | Validação de credenciais inválidas | Alta       |
| RF03      | Campos obrigatórios no login       | Alta       |
| RF04      | Espaços extras nas credenciais     | Alta       |
| RF05      | Recuperação de senha               | Alta       |
| RF06      | Persistência da sessão             | Alta       |
| RF07      | Controle de acesso ao dashboard    | Alta       |
| RF08      | Página inicial do dashboard        | Alta       |
| RF09      | Dashboard                          | Média      |
| RF10      | Gestão de clientes                 | Alta       |
| RF11      | Gestão de matrículas               | Alta       |
| RF12      | Contas a receber                   | Alta       |
| RF13      | Contas a pagar                     | Média      |
| RF14      | Caixas                             | Média      |
| RF15      | Check-in e presenças               | Média      |
| RF16      | Avaliações físicas                 | Média      |
| RF17      | Colaboradores                      | Média      |
| RF18      | Cadastros de apoio                 | Média      |

**Cenário de cada requisito:** C01 cobre RF01 a RF07. C02 cobre RF08. C03 a C12 cobrem RF09 a RF18, na mesma ordem (C03 = RF09, C04 = RF10 e assim por diante).

---

### 🐞 10. **Gestão de Defeitos**

- Bugs são documentados em `3-Relatorio-de-Bugs.md` com:
  - Título
  - Descrição
  - Passos para reproduzir
  - Comportamento esperado e comportamento obtido
  - Evidência em vídeo
  - Severidade (Crítica, Alta, Média, Baixa)
  - Prioridade de correção e status

---

### 📌 11. **Riscos Identificados**

| Risco                                                                             | Impacto | Mitigação                                                      |
| --------------------------------------------------------------------------------- | ------- | -------------------------------------------------------------- |
| A versão do sistema não foi registrada                                            | Médio   | Anotar a versão na próxima execução                            |
| O erro 500 no login inválido esconde a mensagem de credencial incorreta           | Alto    | Conferir a resposta de `POST /api/login` além do texto da tela |
| Os testes de formulário vazio criaram 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12) | Médio | Excluir os registros depois de gravar os vídeos dos BUG-030, 031 e 032 |
| A sessão se comporta de um jeito no retorno ao sistema e de outro no `/dashboard` | Alto    | Repetir os dois caminhos no mesmo vídeo, como no BUG-005       |

---

### 📁 12. **Entregáveis**

- Plano de Testes
- Análise de requisitos
- Casos de teste do login, da página inicial e dos demais módulos; os casos novos aguardam o vídeo ([PENDENTE VÍDEO])
- Roteiro dos vídeos a gravar (`5-Roteiro-de-videos.md`)
- Relatório de bugs com vídeos
- Relatório final de execução
