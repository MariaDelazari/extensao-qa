## Cenário 02: Página inicial do dashboard.

### Caso de Teste 01: Abrir a página inicial depois do login.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C02-CT01 | O usuário autenticado vê a saudação e a data na página inicial. |

| **Pré-condições**                                    |
| :--------------------------------------------------- |
| A conta de teste está autenticada, como no C01-CT01. |

| **Passos**                                                               |
| :----------------------------------------------------------------------- |
| **DADO** que o login foi concluído                                       |
| **QUANDO** a rota `/dashboard` terminar de carregar                      |
| **ENTÃO** a saudação mostra o nome da conta autenticada e a data de hoje |
| **E** o texto "Aqui está o resumo da sua academia hoje" fica visível     |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| A página inicial abre em `/dashboard`, com a data e o nome de quem entrou. |

| **Resultado da execução**                                                                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A saudação mostra "Jair" em vez do nome da conta autenticada. Em outra execução, o caso passou. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: cards exibidos; período padrão 01/10/2026 a 31/10/2026. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/67051a38-ef40-40f3-9179-3ded2aadb3bc) |

---

### Caso de Teste 02: Radar de evasão.

| ID       | Descrição                                                                                                                   |
| :------- | :-------------------------------------------------------------------------------------------------------------------------- |
| C02-CT02 | Verificar se a quantidade de alunos em risco é a mesma no card, no "Radar de Evasão" e no bloco "Inteligência de Retenção". |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                                                            |
| **E** observamos o card "alunos em risco de evasão" e o bloco "Inteligência de Retenção"                          |
| **QUANDO** clicarmos em "Ver detalhes" do card de risco                                                           |
| **ENTÃO** a quantidade de alunos em risco deverá ser a mesma no card, no "Radar de Evasão" e no bloco de retenção |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| Os indicadores de risco de evasão devem ser coerentes entre si. |

| **Resultado da execução**                                                                                                                                                                                                                                                              |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Em 25/10/2026, o rodapé aparece como "Exibindo 3 a 4 de 4 alunos em risco", com quatro linhas na tabela. A gravação não mostra o arquivo exportado nem um aviso. O Jam desse vídeo não trouxe registro de rede, então não dá para afirmar que a requisição deixou de sair. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/5d2ad698-91fa-4d9f-a9f0-64f26dc274dc) |

---

### Caso de Teste 03: Clientes ausentes.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C02-CT03 | Verificar se a quantidade de clientes ausentes da Página Inicial é coerente com a tela de Clientes. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                        |
| :---------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                            |
| **E** observamos o card "Clientes Ausentes"                       |
| **QUANDO** acessarmos a tela de Clientes                          |
| **ENTÃO** o indicador "Ausentes" deverá exibir a mesma quantidade |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| A quantidade de clientes ausentes deve ser igual nas duas telas. |

| **Resultado da execução**                                          |
| :----------------------------------------------------------------- |
| **Falhou.** A Página Inicial exibe 4 e a tela de Clientes exibe 0. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/7cde0ad8-fe3a-4a3b-9a14-0805dca3875b) |

---

### Caso de Teste 04: Clientes sem matrícula.

| ID       | Descrição                                                                           |
| :------- | :---------------------------------------------------------------------------------- |
| C02-CT04 | Verificar se o card "Sem Matrículas" exibe a lista de clientes sem matrícula ativa. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                           |
| :--------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                                               |
| **QUANDO** clicarmos no card "Sem Matrículas"                                                        |
| **ENTÃO** deverá ser exibida a lista de clientes sem matrícula ativa, com a mesma quantidade do card |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| A lista deve apresentar a mesma quantidade informada no card. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1341e429-03e5-4ef6-84bd-9595ba1f5ad5) |

---

### Caso de Teste 05: Desistências no período.

| ID       | Descrição                                                                     |
| :------- | :---------------------------------------------------------------------------- |
| C02-CT05 | Verificar se o card "Desistências no Período" lista as matrículas canceladas. |

| **Pré-condições**                                                              |
| :----------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem matrículas canceladas no período. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial e o card "Desistências no Período" exibe 3 |
| **QUANDO** clicarmos no card "Desistências no Período"                            |
| **ENTÃO** deverão ser listadas as 3 desistências, com código, nome, data e motivo |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| A lista de desistências deve corresponder ao total informado. |

| **Resultado da execução**                                                     |
| :---------------------------------------------------------------------------- |
| **Falhou.** A janela informa que não há desistências, mas exibe o total de 3. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/9b8a90d6-7d67-426f-8c6b-48eb4b8e1296) |

---

### Caso de Teste 06: Financeiro em aberto.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C02-CT06 | Verificar se o detalhe do valor em aberto exibe as mensalidades pendentes. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem mensalidades pendentes. |

| **Passos**                                                                                 |
| :----------------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                                     |
| **QUANDO** clicarmos em "Ver detalhes" do card "em aberto"                                 |
| **ENTÃO** deverá ser exibida a janela "Financeiro em Aberto" com as mensalidades pendentes |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve exibir o detalhamento das mensalidades em aberto. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/224185a5-a0f6-4082-9d54-b8355fb55065) |

---

### Caso de Teste 07: Links de navegação da Página Inicial.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C02-CT07 | Verificar se os links da Página Inicial direcionam para as telas corretas. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                    |
| :---------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                                                                        |
| **QUANDO** clicarmos em "Ver avaliações", "Ver análise completa" e "Ver todos" (Últimas entradas)                             |
| **ENTÃO** deveremos ser direcionados, respectivamente, às telas de Avaliações pendentes, Inteligência & Automação e Presenças |

| **Critérios de aceitação**                            |
| :---------------------------------------------------- |
| Cada link deve direcionar para a tela correspondente. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ebe16560-9f44-4e26-9e7a-1eb6d9e48a49) |

---

### Caso de Teste 08: Abrir as avaliações pendentes pelo card.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C02-CT08 | O card de avaliações pendentes abre a lista filtrada pelo mesmo status. |

| **Pré-condições**                                           |
| :---------------------------------------------------------- |
| A página inicial `/dashboard` está aberta no Sifit Unialfa. |

| **Passos**                                                                   |
| :--------------------------------------------------------------------------- |
| **DADO** que estamos na página inicial                                       |
| **QUANDO** abrimos o detalhe das avaliações pendentes                        |
| **ENTÃO** a rota `/avaliacoes?status=pendente` abre a tela Avaliações        |
| **E** a quantidade do card é a mesma quantidade da lista com status Pendente |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| O número do card e a lista filtrada contam as mesmas avaliações pendentes. |

| **Resultado da execução**                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Em 15/11/2026 o card mostra "1 avaliações pendentes" e a lista filtrada por Pendente mostra 5 avaliações. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/32d0c4a0-db6d-4f38-9f3a-eeceee068739) |

---

### Caso de Teste 09: Filtro de período com data inicial maior que a final.

| ID       | Descrição                                                                                         |
| :------- | :------------------------------------------------------------------------------------------------ |
| C02-CT09 | Verificar se o sistema impede ou alerta sobre um período com data inicial posterior à data final. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                               |
| **E** selecionamos 31/10/2026 como data inicial                                      |
| **QUANDO** selecionarmos 01/10/2026 como data final                                  |
| **ENTÃO** o sistema deverá bloquear a seleção ou exibir um aviso de período inválido |

| **Critérios de aceitação**                |
| :---------------------------------------- |
| Um período invertido não deve ser aceito. |

| **Resultado da execução**                                                                                       |
| :-------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Período 31/10 a 01/10 aceito sem aviso; cards seguem exibindo dados (ex.: 2 matrículas no período). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/5f7f9e52-3989-42d5-99c2-66b747dec9e3) |

---

### Caso de Teste 10: Conferir os cards do resumo da academia.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C02-CT10 | Os cards do resumo mostram quantidades, sem exigir um número fixo. |

| **Pré-condições**                          |
| :----------------------------------------- |
| A página inicial `/dashboard` está aberta. |

| **Passos**                                                                                                                                       |
| :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na página inicial                                                                                                           |
| **QUANDO** olhamos a área de resumo                                                                                                              |
| **ENTÃO** aparecem os cards de alunos em risco de evasão, valor em aberto, pico de movimento e avaliações pendentes                              |
| **E** também aparecem Clientes Ativos, Clientes Ausentes, Sem Matrículas, Personais, Matrículas no Período, Desistências no Período e Renovações |

| **Critérios de aceitação**                          |
| :-------------------------------------------------- |
| Cada card do resumo está visível e mostra um valor. |

| **Resultado da execução**                                                                                                                                                                                                                |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Os cards aparecem, mas o rodapé do Radar de Evasão, a cobrança de Rafael Santos e o valor em aberto não fecham com o detalhe. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso falhou: o card exibe "R$ 0,00 em aberto". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/798502ef-5170-4d69-a87a-fe8cc504d77a) |
