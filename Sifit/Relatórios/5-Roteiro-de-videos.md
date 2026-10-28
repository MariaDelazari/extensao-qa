# Roteiro dos vídeos a gravar

Este arquivo diz o que gravar no Jam para fechar as evidências pendentes. Cada vídeo tem a tela, as ações, o resultado a mostrar e onde colar o link.

Ambiente: https://sifitalfa.centrion.com.br/ — login `marcelo_zandonadi`, senha `Password`, Google Chrome.

Como usar:

1. Grave o vídeo no Jam, com o título indicado (padrão do trabalho: caso `NN - ...`, bug `NN - [BUG] ...`).
2. Troque `[PENDENTE VÍDEO]` do caso por `[Vídeo](link)`.
3. Troque `[PENDENTE BUGS]` do bug por `[BUG:NN](link)`.
4. Se o resultado do vídeo for diferente do descrito aqui, corrija o caso e o bug antes de colar o link. Os resultados deste roteiro foram observados em 28/10/2026 por execução automatizada no Chrome, e o vídeo é o que confirma.
5. Nas telas de Atividades, Objetivos de Treino e Tipos de Pagamento, o teste de 28/10/2026 deixou registros em branco. Exclua esses registros antes de gravar V24, V25 e V26 para a lista voltar ao estado de antes.

Vídeos que podem ser compartilhados entre caso e bug seguem o padrão do trabalho: um vídeo, o mesmo link no caso e no bug.

---

### V01 - Dashboard: título errado

- **Tela:** /dash (menu Dashboard)
- **Ações:**
  1. Entrar com marcelo_zandonadi.
  2. Clicar em "Dashboard" no menu lateral.
  3. Parar 3 segundos no topo da página, mostrando o caminho "Início > Despesas Fixas" e o título "Despesas Fixas".
- **Resultado a demonstrar:** O conteúdo é o do Dashboard (Inteligência Sifit e gráficos), mas o título é "Despesas Fixas".
- **Colar o link em (caso):** C03-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-012 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `03 - Dashboard: título da página`; bug: `01 - [BUG] Dashboard: título mostra Despesas Fixas`

---

### V02 - Dashboard: títulos dos gráficos

- **Tela:** /dash, tema Claro
- **Ações:**
  1. Abrir o Dashboard no tema Claro.
  2. Rolar devagar passando pelos blocos Clientes, Matrículas, Contas a Receber, Cancelamentos e Avaliações.
  3. Parar em cada título para mostrar que quase não dá para ler.
- **Resultado a demonstrar:** Títulos dos blocos e dos gráficos com contraste ruim.
- **Colar o link em (caso):** C03-CT02 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-013 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `04 - Dashboard: títulos dos gráficos`; bug: `02 - [BUG] Dashboard: títulos dos gráficos ilegíveis`

---

### V03 - Alunos em risco em 3 lugares

- **Tela:** Página Inicial e /dash
- **Ações:**
  1. Abrir a Página Inicial e mostrar "1 alunos em risco de evasão".
  2. Rolar até "Inteligência de Retenção" e mostrar 0 alto, 4 médio e 0 baixo.
  3. Abrir o Dashboard e mostrar "0 Alunos em risco".
- **Resultado a demonstrar:** Três valores diferentes para a mesma informação.
- **Colar o link em (caso):** C03-CT03 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-014 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `05 - Alunos em risco entre as telas`; bug: `03 - [BUG] Alunos em risco divergem entre as telas`

---

### V04 - Avaliações pendentes: card x lista

- **Tela:** Página Inicial e /avaliacoes?status=pendente
- **Ações:**
  1. Abrir a Página Inicial e mostrar "0 avaliações pendentes".
  2. Clicar em "Ver detalhes" do card.
  3. Mostrar a lista filtrada por Pendente e contar as 4 linhas (#79, #69, #67, #52).
- **Resultado a demonstrar:** Card com 0 e lista com 4 pendentes.
- **Colar o link em (caso):** C02-CT03 (acrescentar a este caso, que já tem vídeo antigo) — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-015 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `Atualizar a descrição do vídeo do C02-CT03`; bug: `04 - [BUG] Card de avaliações pendentes mostra 0 e a lista tem 4`

---

### V05 - Clientes: paginação

- **Tela:** /clientes
- **Ações:**
  1. Abrir Clientes sem mudar o filtro (Status "Ativo").
  2. Mostrar que a tabela tem 1 cliente (408 - Lila) e o card "Clientes Ativos" mostra 1.
  3. Apontar a paginação "1 2 3" abaixo da tabela.
  4. Mudar Status para "Todos", clicar em Buscar e mostrar 122 clientes.
- **Resultado a demonstrar:** Paginação com 3 páginas para 1 resultado.
- **Colar o link em (caso):** C04-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-016 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `06 - Clientes: listagem e paginação`; bug: `05 - [BUG] Clientes: paginação mostra 3 páginas para 1 resultado`

---

### V06 - Clientes: busca por nome e código

- **Tela:** /clientes
- **Ações:**
  1. Mudar Status para "Todos".
  2. Digitar "mar" em Nome e clicar em Buscar (17 clientes).
  3. Trocar para "MAR" e buscar de novo (17 clientes).
  4. Limpar o nome, digitar 242 em Código e buscar (1 cliente: Ricardo Ford).
- **Resultado a demonstrar:** Busca parcial sem diferenciar maiúsculas e busca por código funcionando.
- **Colar o link em (caso):** C04-CT02, C04-CT03 — trocar `[PENDENTE VÍDEO]`
- **Título sugerido no Jam:** caso: `07 - Clientes: busca por nome e por código`

---

### V07 - Clientes: letras no código

- **Tela:** /clientes
- **Ações:**
  1. Clicar no campo Código.
  2. Digitar "abc" e mostrar que as letras ficam no campo.
- **Resultado a demonstrar:** O campo aceita letras.
- **Colar o link em (caso):** C04-CT04 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-017 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `08 - Clientes: letras no campo código`; bug: `06 - [BUG] Clientes: campo código aceita letras`

---

### V08 - Clientes: cadastro vazio

- **Tela:** /adicionar-cliente
- **Ações:**
  1. Em Clientes, clicar em "Novo Cliente".
  2. Sem preencher nada, clicar em "Cadastrar Cliente".
  3. Mostrar a mensagem "Preencha o nome da pessoa" e que a tela não muda.
- **Resultado a demonstrar:** Cadastro bloqueado com aviso.
- **Colar o link em (caso):** C04-CT05 — trocar `[PENDENTE VÍDEO]`
- **Título sugerido no Jam:** caso: `09 - Clientes: cadastro com campos vazios`

---

### V09 - Matrículas: listagem e cadastro sem cliente

- **Tela:** /matriculas e /adicionar-matricula
- **Ações:**
  1. Abrir Matrículas e mostrar indicadores e lista.
  2. Clicar em "Cadastrar Matrícula".
  3. Sem escolher o cliente, clicar em "Salvar" e mostrar "Selecione o cliente!".
- **Resultado a demonstrar:** Indicadores carregados e salvamento bloqueado.
- **Colar o link em (caso):** C05-CT01, C05-CT02 — trocar `[PENDENTE VÍDEO]`
- **Título sugerido no Jam:** caso: `10 - Matrículas: listagem e cadastro sem cliente`

---

### V10 - Matrículas ativas x clientes ativos

- **Tela:** /matriculas e /clientes
- **Ações:**
  1. Abrir Matrículas e mostrar as 3 matrículas ATIVO (242 Marcelo Longo Zandonadi, 241 Rafaela Andrade, 240 Lila).
  2. Abrir Clientes com Status "Ativo" e mostrar só 1 cliente (Lila).
  3. Mudar para "Todos", buscar "Marcelo" e "Rafaela" e mostrar INATIVO.
- **Resultado a demonstrar:** Matrículas ativas de clientes inativos.
- **Colar o link em (caso):** C05-CT03 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-018 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `11 - Matrículas ativas e clientes ativos`; bug: `07 - [BUG] Matrículas ativas pertencem a clientes inativos`

---

### V11 - Contas a Receber: totais

- **Tela:** /contas-receber
- **Ações:**
  1. Abrir Contas a Receber com o período do mês.
  2. Mostrar "Entradas R$ 499,50" e "Recebido no Mês R$ 475,00 (100,00% recebido)".
  3. Rolar até a lista e mostrar a conta 1608 (a receber R$ 75,50, recebido R$ 100,00).
- **Resultado a demonstrar:** Totais diferentes e valor recebido acima do devido.
- **Colar o link em (caso):** C06-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-019 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `12 - Contas a Receber: totais e listagem`; bug: `08 - [BUG] Contas a Receber: totais não fecham com a lista`

---

### V12 - Contas a Pagar: erro 500

- **Tela:** /contas-pagar
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Contas a Pagar, clicar em "Nova Conta".
  3. Sem preencher nada, clicar em salvar.
  4. Mostrar a mensagem "Erro ao salvar conta a pagar" e a requisição `cadastrar-conta-pagar` com status 500.
- **Resultado a demonstrar:** Erro de servidor em vez de aviso de campos obrigatórios.
- **Colar o link em (caso):** C07-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-020 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `13 - Contas a Pagar: nova conta vazia`; bug: `09 - [BUG] Contas a Pagar: erro 500 ao salvar conta vazia`

---

### V13 - Caixas: erro 500

- **Tela:** /caixas
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Caixas, clicar em "Abrir Caixa".
  3. Sem preencher nada, confirmar.
  4. Mostrar "Erro no servidor. Erro interno inesperado." e a requisição `abrir-caixa` com status 500.
- **Resultado a demonstrar:** Erro de servidor em vez de aviso.
- **Colar o link em (caso):** C08-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-021 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `14 - Caixas: abrir caixa vazio`; bug: `10 - [BUG] Caixas: erro 500 ao abrir caixa vazio`

---

### V14 - Check-in: indicadores x lista

- **Tela:** /checkin e /presencas
- **Ações:**
  1. Abrir Check-in.
  2. Mostrar "3 Check-ins hoje", "Presentes agora 0" e "0% da meta".
  3. Mostrar a tabela com "Nenhum registro encontrado".
  4. Abrir Presenças e mostrar "Nenhuma presença encontrada".
- **Resultado a demonstrar:** Indicador com 3 check-ins e lista vazia.
- **Colar o link em (caso):** C09-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-022 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `15 - Check-in: indicadores e lista`; bug: `11 - [BUG] Check-in: 3 check-ins hoje e lista vazia`

---

### V15 - Pico de movimento

- **Tela:** Página Inicial e /checkin
- **Ações:**
  1. Na Página Inicial, mostrar "Pico de movimento 00h - 01h".
  2. Abrir Check-in e mostrar "Horário de maior movimento: 18h às 20h".
- **Resultado a demonstrar:** Dois horários diferentes.
- **Colar o link em (caso):** C09-CT02 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-023 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `16 - Pico de movimento entre as telas`; bug: `12 - [BUG] Pico de movimento diferente entre as telas`

---

### V16 - Avaliação sem aluno

- **Tela:** /avaliacoes
- **Ações:**
  1. Em Avaliações, clicar em "Cadastrar Avaliação".
  2. Sem escolher o aluno, clicar em "Salvar".
  3. Mostrar o aviso "Selecione um aluno.".
- **Resultado a demonstrar:** Salvamento bloqueado com aviso.
- **Colar o link em (caso):** C10-CT01 — trocar `[PENDENTE VÍDEO]`
- **Título sugerido no Jam:** caso: `17 - Avaliações: cadastro sem aluno`

---

### V17 - Colaboradores: erro 500

- **Tela:** /adicionar-colaborador
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Colaboradores, clicar em "Novo Colaborador".
  3. Sem preencher nada, clicar em "Salvar".
  4. Mostrar "Erro no servidor. Erro interno inesperado." e `salvar/colaborador` com status 500.
- **Resultado a demonstrar:** Erro de servidor em vez de aviso.
- **Colar o link em (caso):** C11-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-024 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `18 - Colaboradores: cadastro vazio`; bug: `13 - [BUG] Colaboradores: erro 500 ao salvar vazio`

---

### V18 - Cadastros de apoio que validam o nome (um vídeo só)

- **Tela:** Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios e Categorias Crossfit
- **Ações:**
  1. Em cada tela, abrir o formulário de novo cadastro.
  2. Clicar em salvar sem preencher.
  3. Mostrar o aviso (por exemplo "Informe o nome do fornecedor.") e passar para a próxima tela.
  4. Ordem: Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios, Categorias Crossfit.
- **Resultado a demonstrar:** Cada tela avisa que o nome é obrigatório e não salva.
- **Colar o link em (caso):** C12-CT02, C12-CT03, C12-CT07, C12-CT08, C12-CT11, C12-CT12, C12-CT13 — trocar `[PENDENTE VÍDEO]`
- **Título sugerido no Jam:** caso: `19 - Cadastros de apoio: nome obrigatório`

---

### V19 - Planos: salvar vazio sem aviso

- **Tela:** /planos
- **Ações:**
  1. Em Planos, clicar em "Novo Plano".
  2. Sem preencher nada, clicar em "Salvar Plano".
  3. Esperar 5 segundos mostrando que nada aparece.
- **Resultado a demonstrar:** Nenhuma mensagem e nenhuma resposta.
- **Colar o link em (caso):** C12-CT01 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-025 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `20 - Planos: salvar vazio`; bug: `14 - [BUG] Planos: salvar vazio não mostra mensagem`

---

### V20 - Prospecção: salvar vazio sem aviso

- **Tela:** /prospeccao
- **Ações:**
  1. Em Prospecção, clicar em "Adicionar Lead".
  2. Sem preencher nada, clicar em "Salvar Lead".
  3. Esperar 5 segundos mostrando que nada aparece.
- **Resultado a demonstrar:** Nenhuma mensagem e nenhuma resposta.
- **Colar o link em (caso):** C12-CT04 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-026 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `21 - Prospecção: salvar vazio`; bug: `15 - [BUG] Prospecção: salvar vazio não mostra mensagem`

---

### V21 - Funções: salvar vazio sem aviso

- **Tela:** /funcoes
- **Ações:**
  1. Em Funções, clicar em "Nova Função".
  2. Sem preencher nada, clicar em "Salvar Função".
  3. Esperar 5 segundos mostrando que nada aparece.
- **Resultado a demonstrar:** Nenhuma mensagem e nenhuma resposta.
- **Colar o link em (caso):** C12-CT05 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-027 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `22 - Funções: salvar vazio`; bug: `16 - [BUG] Funções: salvar vazio não mostra mensagem`

---

### V22 - Produtos: erro genérico

- **Tela:** /produtos
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Produtos, clicar em "Novo" e depois em "Salvar" sem preencher.
  3. Mostrar "Erro ao salvar produto" e `criar-produto` com status 400.
- **Resultado a demonstrar:** Erro sem indicar o campo.
- **Colar o link em (caso):** C12-CT06 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-028 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `23 - Produtos: salvar vazio`; bug: `17 - [BUG] Produtos: erro genérico ao salvar vazio`

---

### V23 - Enquetes: erro genérico

- **Tela:** /enquetes
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Enquetes, clicar em "Nova Enquete" e depois em "Salvar" sem preencher.
  3. Mostrar "Erro ao salvar enquete" e `enquete/salvar` com status 200.
- **Resultado a demonstrar:** Erro sem indicar o campo.
- **Colar o link em (caso):** C12-CT09 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-029 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `24 - Enquetes: salvar vazio`; bug: `18 - [BUG] Enquetes: erro genérico ao salvar vazia`

---

### V24 - Atividades: registro em branco

- **Tela:** /atividades
- **Ações:**
  1. Em Atividades, mostrar o total antes (se já existir a linha 5 em branco criada nos testes, exclua antes de gravar, para o total voltar a 4).
  2. Clicar em "Nova Atividade" e em "Salvar" sem preencher.
  3. Mostrar a nova linha sem nome e o total subindo para 5.
- **Resultado a demonstrar:** Registro em branco criado.
- **Colar o link em (caso):** C12-CT10 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-030 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `25 - Atividades: salvar vazio`; bug: `19 - [BUG] Atividades: salvar vazio cria registro em branco`

---

### V25 - Objetivos de Treino: registro em branco

- **Tela:** /objetivos-treino
- **Ações:**
  1. Em Objetivos de Treino, mostrar a lista sem registros (se já existir o objetivo 1 em branco criado nos testes, exclua antes de gravar).
  2. Clicar em "Novo Objetivo" e em "Salvar" sem preencher.
  3. Mostrar a linha 1 sem nome.
- **Resultado a demonstrar:** Registro em branco criado.
- **Colar o link em (caso):** C12-CT14 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-031 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `26 - Objetivos de Treino: salvar vazio`; bug: `20 - [BUG] Objetivos de Treino: salvar vazio cria registro em branco`

---

### V26 - Tipos de Pagamento: registro em branco

- **Tela:** /tipos-pagamento
- **Ações:**
  1. Em Tipos de Pagamento, mostrar o total (se já existir a linha 12 em branco criada nos testes, exclua antes de gravar, para o total voltar a 10).
  2. Clicar em "Novo" e em "Salvar" sem preencher.
  3. Mostrar a linha 12 sem nome e o total em 11.
- **Resultado a demonstrar:** Registro em branco criado.
- **Colar o link em (caso):** C12-CT15 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-032 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `27 - Tipos de Pagamento: salvar vazio`; bug: `21 - [BUG] Tipos de Pagamento: salvar vazio cria registro em branco`

---

### V27 - Perguntas de Anamnese: erro 500

- **Tela:** /perguntas-anamnese
- **Ações:**
  1. Abrir o DevTools na aba Network.
  2. Em Perguntas, clicar em "Nova Pergunta" e em "Salvar" sem preencher.
  3. Mostrar "Erro ao salvar pergunta" e `pergunta-anamnese/salvar` com status 500.
- **Resultado a demonstrar:** Erro de servidor em vez de aviso.
- **Colar o link em (caso):** C12-CT16 — trocar `[PENDENTE VÍDEO]`
- **Colar o link em (bug):** BUG-033 — trocar `[PENDENTE BUGS]`
- **Título sugerido no Jam:** caso: `28 - Perguntas de Anamnese: salvar vazio`; bug: `22 - [BUG] Perguntas de Anamnese: erro 500 ao salvar vazia`

---
