## Cenário 26: Relatórios.

### Caso de Teste 01: Acesso à tela de Relatórios e textos da interface.

| ID       | Descrição                                                                                                      |
| :------- | :------------------------------------------------------------------------------------------------------------- |
| C26-CT01 | Verificar se a tela de Relatórios exibe os cards, o formulário, os 7 modelos e textos corretamente acentuados. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                               |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                               |
| **QUANDO** acessarmos o menu "FINANCEIRO > Relatórios" (`/relatorios`)                                                                   |
| **ENTÃO** a tela deverá exibir os 4 cards do topo, o formulário de geração e os 7 tipos de relatório com ortografia e acentuação corretas |

| **Critérios de aceitação**                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| A tela deve carregar todos os componentes corretamente e apresentar rótulos e opções de filtros legíveis e acentuados. |

| **Resultado da execução**                                                                                                                                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tela carrega os 4 cards (`Relatorios: 7`, `Filtros ativos: 2`, `Periodo: Definido`, `Saida: PDF`) e os 7 modelos, mas apresenta falta generalizada de acentuação (`Relatorios`, `Periodo`, `Saida`, `Gerar Relatorio`, `Data Inicio`, `Avaliacoes`, `Matriculas`, `Modelos disponiveis`, `situacao`, `Historico`, `fisicas`) e opções em branco no filtro `Tipo de Pagamento`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ce450478-9a53-4d39-bedb-b7e7af98f9fe) |

---

### Caso de Teste 02: Alternância entre os 7 tipos de relatório e filtros dinâmicos.

| ID       | Descrição                                                                                                       |
| :------- | :-------------------------------------------------------------------------------------------------------------- |
| C26-CT02 | Verificar se a troca entre os 7 modelos atualiza os filtros exibidos e o indicador "Filtros ativos".            |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                         |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela `/relatorios`                                                                                                                         |
| **QUANDO** alternarmos entre os 7 modelos pelo seletor `Tipo de Relatorio` e pela coluna direita `Tipos` (`Avaliacoes`, `Clientes`, `Colaboradores`, `Matriculas`, `Contas a Receber`, `Contas a Pagar`, `Caixas`) |
| **ENTÃO** o formulário deverá exibir os filtros específicos de cada tipo (`Planos`/`Tipo de Plano` em Matrículas; `Tipo de Pagamento`/`Status`/`Detalhado` em Contas a Receber; `Formato` em Caixas) e atualizar o card `Filtros ativos` |

| **Critérios de aceitação**                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| Os 7 tipos devem sincronizar entre a coluna lateral e o seletor, exibindo seus filtros dinamicamente. |

| **Resultado da execução**                                                                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema alterna entre os 7 modelos e exibe os filtros específicos. Como ponto de melhoria de UX, os cards do topo quase não mudam (`Relatorios: 7` e `Saida: PDF` são fixos) e agregam pouco valor ao usuário. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3bd36817-c737-468e-bdab-79ad0d7c81d0) |

---

### Caso de Teste 03: Geração de relatório PDF válido (Contas a Pagar, Contas a Receber e Caixas Detalhado).

| ID       | Descrição                                                                                                     |
| :------- | :------------------------------------------------------------------------------------------------------------ |
| C26-CT03 | Verificar se os relatórios de Contas a Pagar, Contas a Receber (Detalhado) e Caixas (Detalhado) geram PDF válido. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                   |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o período de `01/11/2026` a `19/11/2026`                                                                                           |
| **QUANDO** gerarmos `Contas a Pagar`, `Contas a Receber` (marcando `Detalhado`, `Tipo de Pagamento = Dinheiro` e `Status = Recebido`) e `Caixas` (`Formato = Detalhado`)     |
| **ENTÃO** o sistema deverá retornar PDFs válidos (`application/pdf`) e efetuar o download normalmente                                                                        |

| **Critérios de aceitação**                                                                |
| :---------------------------------------------------------------------------------------- |
| Os relatórios devem ser gerados com sucesso e baixar arquivos PDF válidos e abríveis.     |

| **Resultado da execução**                                                                                                                        |
| :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** As requisições `POST /api/relatorio/1` retornaram HTTP 200 com `Content-Type: application/pdf` e baixaram arquivos PDF válidos (`relatorio.pdf`). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2e3461ce-091d-4076-a1be-60aa95c46bac) |

---

### Caso de Teste 04: Geração dos relatórios de Avaliações, Clientes, Colaboradores e Caixas (Normal).

| ID       | Descrição                                                                                                      |
| :------- | :------------------------------------------------------------------------------------------------------------- |
| C26-CT04 | Verificar se os relatórios de Avaliações, Clientes, Colaboradores e Caixas (formato Normal) geram PDF válido.  |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                              |
| :-------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o período de `01/11/2026` a `19/11/2026`                                                      |
| **QUANDO** selecionarmos `Avaliacoes`, `Clientes`, `Colaboradores` ou `Caixas` (`Formato = Normal`) e clicarmos em `Gerar Relatorio`    |
| **ENTÃO** o sistema deverá gerar e baixar um PDF válido ou exibir uma mensagem clara de erro                                            |

| **Critérios de aceitação**                                                                                         |
| :----------------------------------------------------------------------------------------------------------------- |
| O sistema deve gerar arquivos PDF válidos para todos os modelos disponíveis e nunca baixar um arquivo vazio/corrompido sem aviso. |

| **Resultado da execução**                                                                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Para os 4 modelos (`Avaliacoes`, `Clientes`, `Colaboradores` e `Caixas` Normal), `POST /api/relatorio/1` retorna HTTP 200 com `Content-Type: text/html; charset=UTF-8` e corpo vazio (0 bytes), fazendo o navegador baixar um `relatorio.pdf` de 0 bytes (corrompido) sem qualquer aviso. Ao alterar `Caixas` para o formato `Detalhado`, o PDF é gerado normalmente. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/58b2c1b6-5cb4-4930-9e72-7c13da351136) |

---

### Caso de Teste 05: Geração do relatório de Matrículas com filtro "Tipo de Plano".

| ID       | Descrição                                                                                     |
| :------- | :-------------------------------------------------------------------------------------------- |
| C26-CT05 | Verificar se o filtro "Tipo de Plano" é aplicado na geração do relatório de Matrículas.       |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                   |
| :----------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o tipo `Matriculas` selecionado e período `01/11/2026` a `19/11/2026` |
| **E** selecionamos `Mensal` no campo `Tipo de Plano` (card `Filtros ativos` muda para `3`)                   |
| **QUANDO** clicarmos em `Gerar Relatorio` e inspecionarmos a requisição `POST /api/relatorio/1` no DevTools  |
| **ENTÃO** o parâmetro do tipo de plano deverá ser enviado à API para filtrar o relatório gerado              |

| **Critérios de aceitação**                                                                        |
| :------------------------------------------------------------------------------------------------ |
| O filtro "Tipo de Plano" selecionado na tela deve ser enviado na requisição e aplicado ao PDF.    |

| **Resultado da execução**                                                                                                                                                                   |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O PDF é baixado, mas o filtro `Tipo de Plano = Mensal` é completamente omitido do payload JSON de `POST /api/relatorio/1`, que envia apenas `plano_id`, `tipo_pagamento_id` e `status`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a8f72746-bcb3-4c64-a6c7-ab3b44d7d969) |

---

### Caso de Teste 06: Geração de relatório com datas vazias.

| ID       | Descrição                                                                                 |
| :------- | :---------------------------------------------------------------------------------------- |
| C26-CT06 | Verificar o comportamento do sistema ao gerar relatório com Data Início e Data Fim vazias. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                   |
| :--------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o tipo `Contas a Pagar` selecionado                                                |
| **E** limpamos os campos `Data Inicio` e `Data Fim` (card `Periodo` muda para `Todos` e `Filtros ativos` muda para `0`)      |
| **QUANDO** clicarmos em `Gerar Relatorio`                                                                                    |
| **ENTÃO** o sistema deverá gerar o relatório de todo o período ou orientar o preenchimento obrigatório das datas, sem erro 500 |

| **Critérios de aceitação**                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------- |
| O sistema deve cumprir o indicado em "Periodo: Todos" ou validar as datas antes do envio, sem retornar erro interno (500). |

| **Resultado da execução**                                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A API `POST /api/relatorio/1` retorna HTTP 500 (`{"verifica_erro":true,"mensagem":"Erro interno inesperado."}`) e a tela exibe o modal `"Erro no servidor"`. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/89535d14-ee34-4aab-b815-362eecce2494) |

---

### Caso de Teste 07: Geração de relatório com período invertido (Data Início maior que Data Fim).

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C26-CT07 | Verificar se o sistema impede a geração de relatório quando a Data Início é posterior à Data Fim.   |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o tipo `Contas a Pagar` selecionado                   |
| **E** informamos `Data Inicio = 21/11/2026` e `Data Fim = 20/11/2026`                           |
| **QUANDO** clicarmos em `Gerar Relatorio`                                                       |
| **ENTÃO** o sistema deverá bloquear a geração e informar que a data inicial é maior que a final |

| **Critérios de aceitação**                                                       |
| :------------------------------------------------------------------------------- |
| O sistema deve validar o intervalo de datas e impedir o envio de período invertido. |

| **Resultado da execução**                                                                                                                                 |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há validação de intervalo: o sistema envia `data_inicial: "2026-11-21"` e `data_final: "2026-11-20"`, recebe HTTP 200 e baixa o PDF sem aviso. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ac40efe0-ff86-4ec1-9022-773abce167b0) |

---

### Caso de Teste 08: Geração de relatório em período sem registros.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C26-CT08 | Verificar se o sistema trata sem erro a geração de relatório em um período sem registros. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o tipo `Contas a Pagar` selecionado |
| **E** informamos `Data Inicio = 01/01/2020` e `Data Fim = 05/01/2020`         |
| **QUANDO** clicarmos em `Gerar Relatorio`                                     |
| **ENTÃO** o sistema deverá responder sem erro interno                         |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve gerar um PDF vazio ou exibir aviso amigável, sem causar erro no servidor. |

| **Resultado da execução**                                                                                           |
| :------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A requisição retornou HTTP 200 (`application/pdf`) e baixou o PDF normalmente, sem erro no servidor.    |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/50cd8fae-3034-48a7-8774-f68c8142fe93) |

---

### Caso de Teste 09: Geração de relatório com ano fora do intervalo válido (ex.: ano 14500).

| ID       | Descrição                                                                                   |
| :------- | :------------------------------------------------------------------------------------------ |
| C26-CT09 | Verificar se os campos de data limitam anos irreais (com mais de 4 dígitos, como `14500`).  |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que estamos em `/relatorios` com o tipo `Contas a Pagar` selecionado  |
| **E** informamos um ano fora de faixa (ex.: `14500`) no campo de data          |
| **QUANDO** clicarmos em `Gerar Relatorio`                                      |
| **ENTÃO** o sistema deverá rejeitar a data inválida e exigir um ano de 4 dígitos dentro de uma faixa razoável |

| **Critérios de aceitação**                                                                       |
| :----------------------------------------------------------------------------------------------- |
| Os campos de data devem validar limites mínimos e máximos de ano antes de gerar o relatório PDF. |

| **Resultado da execução**                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** Os campos de data não limitam o ano: o sistema aceita o ano `14500`, gera o PDF e imprime a data irreal nele. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e186039e-34bd-4dbb-a4a5-90b6f47182ab) |

