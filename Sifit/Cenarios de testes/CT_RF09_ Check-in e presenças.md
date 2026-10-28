## Cenário 09: Check-in e presenças.

### Caso de Teste 01: Conferir os indicadores do Check-in com a lista.

| ID       | Descrição |
| :------- | :-------- |
| C09-CT01 | Os indicadores do Check-in batem com a lista de check-ins. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/checkin` |
| **QUANDO** olhamos o card "Check-ins hoje" e a tabela de check-ins |
| **ENTÃO** a quantidade do card é a mesma quantidade de registros da tabela |
| **E** "Meta do dia" considera os check-ins do dia |

| **Critérios de aceitação** |
| :------------------------- |
| O número de check-ins do dia é igual nos indicadores e na tabela. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** O card mostra "3 Check-ins hoje" e "18% vs ontem", mas a tabela mostra "Nenhum registro encontrado", "Presentes agora" é 0 e "Meta do dia" mostra "0% da meta". |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-022 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V14) |

---

### Caso de Teste 02: Conferir o horário de pico entre as telas.

| ID       | Descrição |
| :------- | :-------- |
| C09-CT02 | O horário de pico é o mesmo na Página Inicial e no Check-in. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que anotamos o card "Pico de movimento" da Página Inicial |
| **QUANDO** abrimos `/checkin` e olhamos "Pico de movimento" |
| **ENTÃO** os dois horários são iguais |

| **Critérios de aceitação** |
| :------------------------- |
| A faixa de horário de pico é igual nas duas telas. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Página Inicial: "00h - 01h". Check-in: "Horário de maior movimento: 18h às 20h". |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-023 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V15) |
