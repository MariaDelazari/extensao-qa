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
| **ENTÃO** a saudação mostra o nome da conta autenticada e a data de hoje |
| **E** o texto "Aqui está o resumo da sua academia hoje" fica visível     |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| A página inicial abre em `/dashboard`, com a data e o nome de quem entrou. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/67051a38-ef40-40f3-9179-3ded2aadb3bc) |

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
| [Vídeo](https://jam.dev/c/798502ef-5170-4d69-a87a-fe8cc504d77a) |

---

### Caso de Teste 03: Abrir as avaliações pendentes pelo card.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C02-CT03 | O card de avaliações pendentes abre a lista filtrada pelo mesmo status.       |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| A página inicial `/dashboard` está aberta no Sifit Unialfa.    |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que estamos na página inicial                                                  |
| **QUANDO** abrimos o detalhe das avaliações pendentes                                   |
| **ENTÃO** a rota `/avaliacoes?status=pendente` abre a tela Avaliações                   |
| **E** a quantidade do card é a mesma quantidade da lista com status Pendente            |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O número do card e a lista filtrada contam as mesmas avaliações pendentes.    |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/4f672eb2-1483-4e93-8181-cea811350409) |
