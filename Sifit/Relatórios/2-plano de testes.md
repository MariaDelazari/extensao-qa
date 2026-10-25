## 🧪 **Plano de Testes - Sifit Centrion**

### 📌 1. **Identificação**

- **Nome do Projeto**: Sifit Centrion
- **Versão Avaliada**: não informada nos registros de execução
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

**Excluído:**

- Módulos internos depois do login, porque a execução registrada ficou na autenticação
- Testes em dispositivos móveis
- Testes de performance ou carga

---

### 🔧 4. **Ferramentas Utilizadas**

- Google Chrome 150.0.7871.46
- Ferramentas de inspeção do navegador (aba Network e console), usadas na análise dos bugs de login
- Jam, para gravar os vídeos de execução
- Markdown e Git, para registrar os casos, os bugs e este plano

---

### 🧪 5. **Técnicas de Teste**

- Caminho feliz
- Testes negativos
- Particionamento de equivalência nos dados de login (válido, inválido, vazio e com espaços)
- Teste exploratório no retorno da sessão e no acesso direto pela URL

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
| Execução dos Testes Manuais | 12/10/2026     | 12/10/2026     |
| Registro e Report de Bugs   | 12/10/2026     | 12/10/2026     |
| Encerramento e Evidências   | 12/10/2026     | 12/10/2026     |

A execução registrada no relatório de bugs começa em 12/10/2026. Em 24/10/2026, os testes passaram para https://sifitalfa.centrion.com.br/. As datas de planejamento e de escrita dos casos não foram anotadas.

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
| A sessão se comporta de um jeito no retorno ao sistema e de outro no `/dashboard` | Alto    | Repetir os dois caminhos no mesmo vídeo, como no BUG-005       |

---

### 📁 12. **Entregáveis**

- Plano de Testes
- Análise de requisitos
- Casos de teste do login
- Relatório de bugs com vídeos
- Relatório final de execução
