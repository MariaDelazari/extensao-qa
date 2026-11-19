# Anotações QA Sifit — Daniel (Branch `daniel`)

> **Lembrete:** remover este arquivo (`ANOTACOES-DANIEL.md`) antes do merge final para a `main`.

---

## 1. O que já foi concluído em 19/11/2026

- **`CT_RF10_ Avaliações.md`**: todos os 12 casos com vídeo no Jam; movido de `Pendentes de evidencias/` para `Sifit/Cenarios de testes/`.
  - Bugs atualizados em `3-Relatorio-de-Bugs.md`: `BUG-066`, `BUG-067`, `BUG-068` (Linux Mint) e `BUG-069` (Windows 11, Chrome `157.0.8103.79`).
- **`CT_RF13_ Contas a pagar e despesas fixas.md`**: todos os 16 casos com vídeo no Jam (nomes ajustados para `Daniel` / `Daniel Satel`); movido de `Pendentes de evidencias/` para `Sifit/Cenarios de testes/`.
  - Bugs atualizados em `3-Relatorio-de-Bugs.md`: `BUG-020`, `BUG-076`, `BUG-077`, `BUG-078`, `BUG-079`, `BUG-080`.
  - Novos bugs registrados (Windows 11, Chrome `157.0.8103.79`, `19/11/2026`):
    - `BUG-149`: Despesa fixa não salva quando o valor é informado com vírgula (aceita apenas ponto) (`C13-CT15`)
    - `BUG-150`: Visualização de conta a pagar com legibilidade ruim no modo escuro (`C13-CT07`)
    - `BUG-151`: Menu lateral perde a posição de rolagem e volta ao topo a cada atualização (`C13-CT08`)
    - `BUG-152`: Ausência de paginação na listagem de Despesas Fixas (`C13-CT10`)
- **2 casos extras executados e gravados**:
  - `C01-CT10` em `CT_RF01_ Login na plataforma.md` (Passou — 2 vídeos: credenciais válidas com 5 cliques rápidos e senha inválida `87654321`).
  - `C06-CT15` em `CT_RF06_ Gestão de matrículas.md` (Passou — ao escolher modalidade com `Data Inicial` e `Data Final`, não permite alterar a data para antes do dia atual ou para o futuro).
- **`2-plano de testes.md`** (seção 13) e **`4- Relatorio dos testes.md`** (linhas de `RF01`, `RF06`, `RF13`, tabela de bugs `BUG-149`–`BUG-152` e nota de `Pendentes de evidencias` vazia) atualizados.
- **Próximo ID livre de bug:** `BUG-153` *(sempre conferir `git pull` antes de criar novos bugs)*.

---

## 2. O que falta fazer (3 telas novas — confirmado com o Ville)

Criar os 3 arquivos de cenário em `Sifit/Cenarios de testes/`, registrar novos bugs em `Sifit/Relatórios/3-Relatorio-de-Bugs.md` (a partir de `BUG-153`), gravar os vídeos no Jam e atualizar `1-Analise de requisitos.md`, `2-plano de testes.md` e `4- Relatorio dos testes.md` (incluindo o recálculo final dos totais).

> **Atenção (fora do escopo):** NÃO acionar nada que dispare mensagem real no **WhatsApp** (ex.: botão `Executar agora` de automações com canal WhatsApp) nem cobrança real no **Pagar.me**.

---

### 2.1. RF26 — Relatórios (`CT_RF26_ Relatórios.md`)

**Observações das prints tiradas em 19/11/2026:**
- Acesso: menu lateral `FINANCEIRO > Relatórios` (breadcrumb `Início > Relatórios`).
- Cards no topo: `Relatorios: 7`, `Filtros ativos: 2` (sobe para `3` em Contas a Receber e Caixas), `Periodo: Definido`, `Saida: PDF`.
- **Achado visual já notado nas prints:** textos da tela sem acentuação (`Relatorios`, `Periodo`, `Saida`, `Gerar Relatorio`, `Avaliacoes`, `Historico de avaliacoes fisicas`, `situacao`, `Matriculas`, `Data Inicio`).
- **7 tipos/modelos disponíveis** (no select `Tipo de Relatorio` e na coluna direita `Tipos`):
  1. `Avaliacoes` (`Historico de avaliacoes fisicas`) — filtros: `Data Inicio`, `Data Fim`
  2. `Clientes` (`Cadastro e situacao dos alunos`) — filtros: `Data Inicio`, `Data Fim`
  3. `Colaboradores` (`Equipe e dados internos`) — filtros: `Data Inicio`, `Data Fim`
  4. `Matriculas` (`Contratos e planos por periodo`) — filtros: `Planos`, `Tipo de Plano`, `Data Inicio`, `Data Fim`
  5. `Contas a Receber` (`Recebimentos por status e pagamento`) — filtros: `Tipo de Pagamento`, `Status`, checkbox `Detalhado` (`Inclui descricao completa por conta`), `Data Inicio`, `Data Fim`
  6. `Contas a Pagar` (`Despesas e pagamentos`) — filtros: `Data Inicio`, `Data Fim`
  7. `Caixas` (`Movimento de caixa normal ou detalhado`) — filtros: `Formato` (`Normal` / `Detalhado`), `Data Inicio`, `Data Fim`

**Ideias de casos de teste (`C26-CT01` a `C26-CT06`):**
1. Acesso à tela de Relatórios (cards, 7 modelos e formulário).
2. Alternância entre os tipos de relatório e exibição dinâmica dos filtros específicos (Matrículas, Contas a Receber, Caixas) + card `Filtros ativos`.
3. Geração de relatório PDF com período válido (testar se baixa/abre o PDF corretamente e se o conteúdo confere).
4. Geração de relatório com filtros específicos (ex.: Contas a Receber com `Detalhado` e Status; Caixas Normal vs Detalhado; Matrículas por Plano).
5. Período inválido (`Data Inicio` maior que `Data Fim`) e datas vazias ao clicar em `Gerar Relatorio`.
6. Período sem registros — verificar se gera PDF vazio, exibe aviso ou dá erro 500.

---

### 2.2. RF27 — Importar Avaliações (`CT_RF27_ Importar avaliações.md`)

**Observações da print tirada em 19/11/2026:**
- Não tem item direto no menu lateral: é acessada entrando em **Avaliações** (`/avaliacoes`) e clicando no botão **`Importar`** (logo abaixo do filtro `Código`).
- Ainda falta abrir a tela/modal ao clicar em **`Importar`** para mapear campos, formatos aceitos, modelo/template e mensagens de erro.

**Ideias de casos de teste (`C27-CT01` a `C27-CT05`):**
1. Acesso à tela/modal de Importar Avaliações a partir do botão `Importar` em `/avaliacoes`.
2. Tentar importar sem selecionar arquivo (validação de obrigatoriedade).
3. Tentar importar arquivo com extensão/formato inválido (ex.: `.txt` ou `.png`).
4. Verificar download de modelo/planilha exemplo (se existir) e comportamento com arquivo malformado/vazio.
5. Importação com arquivo válido (se aplicável sem sujar base com dados inválidos; excluir avaliação criada depois).

---

### 2.3. RF28 — Inteligência & Automação e Resultados IA (`CT_RF28_ Inteligência e automação e Resultados IA.md`)

**Observações das prints tiradas em 19/11/2026:**

#### Tela A — Resultados IA (`/inteligencia/resultados`)
- Menu lateral: `INTELIGÊNCIA > Resultados IA` (breadcrumb `Início > Resultados da Inteligência`).
- Filtros de período: `Hoje`, `Últimos 7 dias`, `Últimos 30 dias`, `Últimos 90 dias`.
- 8 cards indicadores:
  - `Automações executadas`, `Relatórios enviados`, `Alunos em risco identificados`, `Alunos com frequência em queda`, `Aniversariantes encontrados`, `Avaliações vencendo`, `Alunos inadimplentes monitorados`, `Frequência média da academia`.
- Blocos inferiores: `O que o Sifit identificou` e `Automações mais eficientes`.
- Card lateral `Inteligência Sifit`: alertas `Atenção` (`Sua academia possui 1 aluno(s) com risco de evasão.`) e `Financeiro` (`46 aluno(s) inadimplente(s) sendo monitorado(s) pela Inteligência.`).
- **Possível inconsistência já visível na print:** em `Últimos 7 dias`, o card mostra `0 Alunos em risco identificados`, enquanto o card lateral `Inteligência Sifit` mostra `1 aluno(s) com risco de evasão` (verificar se muda nos filtros `Últimos 30 dias` / `90 dias`).

#### Tela B — Inteligência & Automação (`Central de Automações`)
- Menu lateral: `INTELIGÊNCIA > Inteligência & Automação`.
- Banner superior com botão `Atualizar` e 4 cards: `2 automações ativas`, `Última execução (31/10/2026 às 19:09)`, `Canal principal (WhatsApp)`, `Relatórios enviados no mês (—)`.
- **Automações ativas:**
  - `Risco de Evasão` (toggle Ativa, Frequência `Diária`, Canal `WhatsApp + Painel`, botões `Executar agora`, `Configurar`, `Ver resultados`).
  - `Aniversariantes` (toggle Ativa • Nunca executou, Frequência `Personalizada`, Canal `WhatsApp + E-mail`, botões `Executar agora`, `Configurar`).
- **Automações disponíveis:**
  - `Avaliações vencendo` (`Verificar agora`)
  - `Frequência em queda` (`Ver lista`)
  - `Financeiro diário` (`Ver resumo`)
  - `Cobranças automáticas` (`Configurar e ver prévia`)
- **Coluna `Atividade recente` + observações do Daniel:**
  - Lista muito longa de `Risco de evasão` (de `31/10/2026` até `07/10/2026`) **sem scroll próprio** na caixa, alongando toda a página (melhoria/bug de UX: poderia ter barra de rolagem interna).
  - Há registros aparentemente duplicados no mesmo minuto (`31/10/2026 às 19:09` 4 vezes, `22/10/2026 às 16:20` 2 vezes, `08/10/2026 às 17:40` 2 vezes).
  - Cada botão `Configurar` abre diversas configurações personalizadas (inspecionar sem disparar envio real).

**Ideias de casos de teste (`C28-CT01` a `C28-CT08` — sem disparar WhatsApp/Pagar.me):**
1. Acesso à tela `Resultados IA` (`/inteligencia/resultados`) e exibição dos indicadores e cards.
2. Alternância dos filtros de período (`Hoje`, `Últimos 7 dias`, `Últimos 30 dias`, `Últimos 90 dias`) em `Resultados IA` e coerência entre os indicadores e o bloco `Inteligência Sifit`.
3. Acesso à tela `Inteligência & Automação` (`Central de Automações`), botão `Atualizar` e conferência da coluna `Atividade recente` (ausência de scroll interno / registros duplicados).
4. Abertura dos modais `Configurar` (`Risco de Evasão` e `Aniversariantes`) e validação de campos/cancelamento (sem acionar `Executar agora`).
5. Abertura de `Ver resultados` em `Risco de Evasão`.
6. Abertura das ações de visualização/prévia em `Automações disponíveis`: `Verificar agora` (Avaliações vencendo), `Ver lista` (Frequência em queda), `Ver resumo` (Financeiro diário) e `Configurar e ver prévia` (Cobranças automáticas — somente prévia, sem disparar cobrança/WhatsApp).

---

## 3. Nota sobre os 20 bugs sem link do Keltton

No documento do grupo (`QA Sifit – O que cada um faz`, p. 1–2), os 20 bugs ainda sem link em `3-Relatorio-de-Bugs.md` (`BUG-022`, `023`, `027`, `061`, `064`, `081`–`083`, `090`–`092`, `116`–`124`) são responsabilidade do **Keltton**. Não alterar sem combinar com ele para evitar conflito com a branch `keltton`.

---

## 4. Como habilitar o Chrome em casa para o agente testar no navegador

Para o agente conseguir abrir `https://sifitalfa.centrion.com.br/` pelo Chrome DevTools:
1. Abra o **Google Chrome** na máquina onde o Antigravity está rodando.
2. Acesse `chrome://inspect/#remote-debugging` na barra de endereços e habilite o **remote debugging** (para gerar o `DevToolsActivePort` no perfil padrão do Chrome).
3. Envie o prompt da seção 5 abaixo.

---

## 5. Prompt para continuar em casa

```text
Leia o arquivo ANOTACOES-DANIEL.md na raiz do repositório para retomar exatamente de onde paramos na branch daniel.

Já habilitei o remote debugging no Chrome (chrome://inspect/#remote-debugging).

Por favor:
1. Entre no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com usuário "marcelo_zandonadi" e senha "password" usando o navegador.
2. Explore e teste na prática (SEM disparar nenhuma mensagem real no WhatsApp nem cobrança real no Pagar.me) as 3 telas novas que faltam da minha parte:
   - RF26: Relatórios (menu Financeiro > Relatórios)
   - RF27: Importar Avaliações (menu Avaliações > botão "Importar")
   - RF28: Inteligência & Automação e Resultados IA (/inteligencia/resultados)
3. Com base no que você observar no navegador + DevTools + observações em ANOTACOES-DANIEL.md:
   - Crie os arquivos CT_RF26_ Relatórios.md, CT_RF27_ Importar avaliações.md e CT_RF28_ Inteligência e automação e Resultados IA.md em Sifit/Cenarios de testes/Pendentes de evidencias/ (no padrão exato do repositório, deixando [Vídeo](coloque o link do video aqui) para eu gravar no Jam).
   - Registre todos os bugs reais encontrados em Sifit/Relatórios/3-Relatorio-de-Bugs.md a partir do próximo ID livre (conferir depois de git pull; atualmente BUG-153), deixando só o link do Jam pendente.
   - Me devolva a lista objetiva dos vídeos que preciso gravar no Jam para eu te mandar os links e fecharmos tudo (incluindo atualizar 1-Analise de requisitos.md, 2-plano de testes.md, 4- Relatorio dos testes.md e remover ANOTACOES-DANIEL.md antes do merge final).
```
