## Cenário 02: Página inicial do dashboard.

### Caso de Teste 01: Abrir a página inicial depois do login.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C02-CT01 | O usuário autenticado vê a saudação e a data na página inicial. |

| **Pré-condições**                                    |
| :--------------------------------------------------- |
| A conta de teste está autenticada, como no C01-CT01. |

| **Passos**                                                           |
| :------------------------------------------------------------------- |
| **DADO** que o login foi concluído                                   |
| **QUANDO** a rota `/dashboard` terminar de carregar                  |
| **ENTÃO** a saudação mostra o nome Jair e a data de hoje             |
| **E** o texto "Aqui está o resumo da sua academia hoje" fica visível |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| A página inicial abre em `/dashboard`, com a saudação e a data. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 02: Conferir os cards do resumo da academia.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C02-CT02 | Os cards do resumo mostram quantidades, sem exigir um número fixo. |

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

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 03: Conferir a inteligência de retenção.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C02-CT03 | O bloco de retenção mostra risco, saúde da academia e a data da última análise. |

| **Pré-condições**                          |
| :----------------------------------------- |
| A página inicial `/dashboard` está aberta. |

| **Passos**                                                                               |
| :--------------------------------------------------------------------------------------- |
| **DADO** que estamos na página inicial                                                   |
| **QUANDO** localizamos o bloco Inteligência de Retenção                                  |
| **ENTÃO** a tela mostra Alto risco, Médio risco, Baixo risco e o bloco SAÚDE DA ACADEMIA |
| **E** mostra a última análise e o link Ver análise completa                              |

| **Critérios de aceitação**                                                           |
| :----------------------------------------------------------------------------------- |
| O bloco de retenção fica visível, com os três níveis de risco e a saúde da academia. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 04: Ver as ações recomendadas sem disparar mensagem.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C02-CT04 | As ações do dia aparecem, e os botões de cobrança não são acionados. |

| **Pré-condições**                          |
| :----------------------------------------- |
| A página inicial `/dashboard` está aberta. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que estamos na página inicial                                                |
| **QUANDO** localizamos Ações recomendadas para hoje                                   |
| **ENTÃO** a tela mostra as ações de cobrança, de contato com inativos e de avaliações |
| **E** não clicamos em Cobrar agora, Enviar mensagem nem Cobrar todos no WhatsApp      |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| As ações ficam visíveis e nenhuma mensagem é enviada aos alunos. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 05: Conferir movimento, mensalidades, agenda, entradas e aniversariantes.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C02-CT05 | Os blocos inferiores da página inicial carregam lista ou estado vazio. |

| **Pré-condições**                          |
| :----------------------------------------- |
| A página inicial `/dashboard` está aberta. |

| **Passos**                                                                                       |
| :----------------------------------------------------------------------------------------------- |
| **DADO** que estamos na página inicial                                                           |
| **QUANDO** descemos a página                                                                     |
| **ENTÃO** aparecem Movimento da Academia por horário e por dia da semana                         |
| **E** aparecem Mensalidades pendentes, Agenda de hoje, Últimas entradas e Aniversariantes do dia |
| **E** a tabela de últimas entradas tem as colunas NOME, UNIDADE e DATA / HORA                    |
| **E** agenda e aniversariantes mostram os itens do dia ou a mensagem de que não há registros     |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| Os cinco blocos carregam. Lista vazia aparece com mensagem, e não como área em branco. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---
