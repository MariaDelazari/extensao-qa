## Cenário 28: Inteligência & Automação e Resultados IA.

### Caso de Teste 01: Acesso à tela Resultados IA (`/inteligencia/resultados`).

| ID       | Descrição                                                                                                      |
| :------- | :------------------------------------------------------------------------------------------------------------- |
| C28-CT01 | Verificar se a tela Resultados IA carrega os filtros de período, os 8 cards indicadores e os blocos inferiores. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                    |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos autenticados no SIFIT                                                                                                                    |
| **QUANDO** acessarmos o menu "INTELIGÊNCIA > Resultados IA" (`/inteligencia/resultados`)                                                                      |
| **ENTÃO** a tela deverá exibir os filtros (`Hoje`, `Últimos 7 dias`, `Últimos 30 dias`, `Últimos 90 dias`), os 8 cards indicadores, `O que o Sifit identificou`, `Automações mais eficientes` e o bloco lateral `Inteligência Sifit` |

| **Critérios de aceitação**                                                                       |
| :----------------------------------------------------------------------------------------------- |
| A tela deve carregar sem erros de API ou console e apresentar todos os componentes previstos.    |

| **Resultado da execução**                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A tela carrega normalmente (`GET /api/inteligencia/resultados/1?periodo=7`, HTTP 200) exibindo todos os filtros, cards e blocos. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ffc9f75d-f9b6-42d7-b8cc-85c93db38ab9) |

---

### Caso de Teste 02: Filtros de período e coerência dos indicadores em Resultados IA.

| ID       | Descrição                                                                                                                |
| :------- | :----------------------------------------------------------------------------------------------------------------------- |
| C28-CT02 | Verificar se os filtros de período atualizam corretamente os indicadores e se os números são coerentes entre os blocos.  |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                               |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela `/inteligencia/resultados`                                                                                  |
| **QUANDO** alternarmos entre os filtros `Hoje`, `Últimos 7 dias`, `Últimos 30 dias` e `Últimos 90 dias`                                  |
| **ENTÃO** os cards indicadores, `O que o Sifit identificou`, `Automações mais eficientes` e `Inteligência Sifit` deverão exibir números coerentes entre si |

| **Critérios de aceitação**                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------- |
| Os números de alunos em risco identificados devem bater entre os cards, a tabela de eficiência e o bloco Inteligência Sifit. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                        |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O card `Alunos em risco identificados` exibe sempre `0` nos 4 períodos, contradizendo o bloco `Inteligência Sifit` (`1 aluno(s) com risco de evasão`) e `Automações mais eficientes` (`48 identificados` em 30 dias e `56 identificados` em 90 dias). Além disso, `Avaliações vencendo` (`1`) e `Alunos inadimplentes monitorados` (`46`) não mudam com o período, e a lista `O que o Sifit identificou` trunca em 15 itens mesmo em 90 dias (com 23 execuções), sem controles de paginação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/8dd4474b-2e63-4f84-a535-6009d8bdb621) |

---

### Caso de Teste 03: Acesso à tela Inteligência & Automação, botão Atualizar e coluna Atividade recente.

| ID       | Descrição                                                                                                                   |
| :------- | :-------------------------------------------------------------------------------------------------------------------------- |
| C28-CT03 | Verificar o carregamento da Central de Automações, o botão Atualizar e a exibição da coluna "Atividade recente".            |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                         |
| :--------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos o menu "INTELIGÊNCIA > Inteligência & Automação" (`/inteligencia-automacao`)                                |
| **QUANDO** clicarmos em `Atualizar` e rolarmos a página observando os cards do topo e a coluna `Atividade recente`                 |
| **ENTÃO** os indicadores devem refletir os dados reais, o histórico não deve ter execuções duplicadas no mesmo minuto e a caixa deve ter rolagem interna |

| **Critérios de aceitação**                                                                                                                |
| :---------------------------------------------------------------------------------------------------------------------------------------- |
| O botão Atualizar deve recarregar os dados sem erro, os registros não devem duplicar no mesmo minuto e a coluna lateral deve ter altura limitada com scroll interno. |

| **Resultado da execução**                                                                                                                                                                                                                                                                |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O botão `Atualizar` recarrega as APIs com HTTP 200, porém: (1) `Atividade recente` possui 20 itens sem altura máxima nem barra de rolagem interna, esticando toda a página; (2) há execuções duplicadas no mesmo minuto (4x em `31/10/2026 às 19:09`, 2x em `22/10/2026 às 16:20`, 2x em `08/10/2026 às 17:40`); (3) `Relatórios enviados no mês` exibe `—` quando a API devolve `0`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/4b0cf5cf-f808-40ca-b1e7-b695ee71c24a) |

---

### Caso de Teste 04: Abertura e inspeção do modal "Configurar" em Risco de Evasão.

| ID       | Descrição                                                                                                       |
| :------- | :-------------------------------------------------------------------------------------------------------------- |
| C28-CT04 | Verificar os campos e canais de envio do modal "Configurar" da automação Risco de Evasão (sem disparar envio).  |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                    |
| :------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos em `/inteligencia-automacao`                                                             |
| **QUANDO** clicarmos em `Configurar` no card `Risco de Evasão`, inspecionarmos os campos e clicarmos em `Cancelar` |
| **ENTÃO** o modal deverá exibir opções coerentes e não permitir marcar "Apenas painel" junto com outros canais |

| **Critérios de aceitação**                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| A opção "Apenas painel" deve ser mutuamente exclusiva com "WhatsApp" e "E-mail", e o botão "Cancelar" deve fechar sem alterar nada. |

| **Resultado da execução**                                                                                                                                                      |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O modal abre e fecha normalmente por `Cancelar`, mas a opção `Apenas painel` aparece marcada simultaneamente com `WhatsApp` (e também com `E-mail` em Aniversariantes), contradizendo o próprio rótulo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f2467c54-cf0f-4c52-9c47-d1f96fc58c08) |

---

### Caso de Teste 05: Visualização de "Ver resultados" em Risco de Evasão.

| ID       | Descrição                                                                                                  |
| :------- | :--------------------------------------------------------------------------------------------------------- |
| C28-CT05 | Verificar se "Ver resultados" em Risco de Evasão lista os alunos contabilizados no resumo de risco.        |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/inteligencia-automacao`                                                    |
| **QUANDO** clicarmos em `Ver resultados` no card `Risco de Evasão`                                   |
| **ENTÃO** o painel deverá listar o aluno contabilizado em médio risco de forma coerente com o resumo |

| **Critérios de aceitação**                                                                       |
| :----------------------------------------------------------------------------------------------- |
| Os totais do resumo, as contagens das abas e a tabela de alunos devem apresentar os mesmos dados. |

| **Resultado da execução**                                                                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O cabeçalho exibe `"1 aluno(s) analisado(s)"` e o card `"1 Médio risco"`, mas a API `GET /api/automacoes/risco-evasao/resultados/1` devolve `alunos: []`, fazendo as abas exibirem `Todos 0` e `Médio 0` com a mensagem `"Nenhum aluno neste nível."`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/d38f763f-92b3-4717-b946-41036f08fa48) |

---

### Caso de Teste 06: Abertura e inspeção do modal "Configurar" em Aniversariantes.

| ID       | Descrição                                                                                                   |
| :------- | :---------------------------------------------------------------------------------------------------------- |
| C28-CT06 | Verificar se o modal "Configurar" de Aniversariantes exibe campos e prévia próprios de aniversariantes.     |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                   |
| :----------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/inteligencia-automacao`                                                            |
| **QUANDO** clicarmos em `Configurar` no card `Aniversariantes`, inspecionarmos os campos e clicarmos em `Cancelar` |
| **ENTÃO** o modal deverá exibir opções e prévia relacionadas a aniversariantes (incluindo destinatário Aluno) |

| **Critérios de aceitação**                                                                                       |
| :--------------------------------------------------------------------------------------------------------------- |
| O modal de Aniversariantes deve apresentar formulário, destinatários e prévia coerentes com a funcionalidade.    |

| **Resultado da execução**                                                                                                                                                                                                                             |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O modal reutiliza o formulário de `Risco de Evasão`, exibindo `Critérios analisados` (`Ausência`, `Inadimplência`, `Baixa frequência`, `Treino abandonado`, `Queda de check-ins`), `Sensibilidade` (`Alta`) e `PREVIEW DO RELATÓRIO` com `"43 alunos em risco"`. Além disso, omite a opção de destinatário `Aluno` (presente no JSON da API) e exibe intervalo de `32 dias`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ec8ef843-f515-4b9c-b892-ff446f0a5584) |

---

### Caso de Teste 07: Consulta das automações disponíveis de leitura (Avaliações vencendo, Frequência em queda e Financeiro diário).

| ID       | Descrição                                                                                                                   |
| :------- | :-------------------------------------------------------------------------------------------------------------------------- |
| C28-CT07 | Verificar o funcionamento e a coerência dos painéis de consulta "Verificar agora", "Ver lista" e "Ver resumo".              |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/inteligencia-automacao`, na seção `Automações disponíveis`                                                                           |
| **QUANDO** clicarmos em `Verificar agora` (`Avaliações vencendo`), `Ver lista` (`Frequência em queda`) e `Ver resumo` (`Financeiro diário`, navegando entre datas) |
| **ENTÃO** os painéis de leitura deverão abrir sem erros e com números coerentes com a tela `Resultados IA`                                                     |

| **Critérios de aceitação**                                                                                           |
| :------------------------------------------------------------------------------------------------------------------- |
| Os painéis de consulta devem abrir com HTTP 200, responder sem erro ao mudar datas e exibir contagens consistentes com Resultados IA. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** `Frequência em queda` (`0 aluno(s)`) carrega normalmente, mas: (1) `Avaliações vencendo` contradiz `Resultados IA`, exibindo `"Nenhum aluno com avaliação vencida para mostrar."` e `"Prazo de 1 dias · 29 de 30 alunos ativos · 29 nunca avaliados"` (erro de plural e divergência com `antecedencia_dias: 7`), enquanto `Resultados IA` informa `Avaliações vencendo: 1`; (2) ao alterar rapidamente a data pelas setas em `Financeiro do dia`, o sistema exibiu `"Erro no servidor"`; (3) a seção exibe `"Em breve trabalhando por você."` mesmo com 7 automações ativas na API. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/08c5a4dc-5745-4cc8-addc-68e15e54d962) |

---

### Caso de Teste 08: Visualização da prévia em "Cobranças automáticas" (sem disparar envio).

| ID       | Descrição                                                                                                      |
| :------- | :------------------------------------------------------------------------------------------------------------- |
| C28-CT08 | Verificar se "Configurar e ver prévia" em Cobranças automáticas abre os parâmetros e a lista prévia sem enviar. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                       |
| :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/inteligencia-automacao`, na seção `Automações disponíveis`                                                             |
| **QUANDO** clicarmos em `Configurar e ver prévia` no card `Cobranças automáticas`, conferirmos a lista prévia e clicarmos em `Fechar` (sem enviar) |
| **ENTÃO** o painel deverá exibir os parâmetros de vencimento, templates de mensagem e prévia de avisos sem disparar cobranças ou mensagens       |

| **Critérios de aceitação**                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------- |
| A tela deve permitir inspecionar a configuração e a prévia de avisos com segurança e fechar sem disparar envios no WhatsApp. |

| **Resultado da execução**                                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O painel `Cobrança automática (WhatsApp)` carrega (`GET /api/automacoes/cobranca/previa/1`, HTTP 200), exibe parâmetros, templates, 2 avisos previstos e mantém `Enviar agora` desabilitado (`WhatsApp não conectado`), fechando normalmente em `Fechar`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/d9f2d202-c067-486b-b331-d5114fef662d) |
