## Cenário 06: Contas a receber.

### Caso de Teste 01: Conferir os totais com a listagem.

| ID       | Descrição |
| :------- | :-------- |
| C06-CT01 | Os totais do topo de Contas a Receber batem com as linhas da listagem. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/contas-receber` com o período do mês |
| **QUANDO** somamos as linhas da listagem |
| **ENTÃO** "Entradas", "Previsto para o Mês" e "Recebido no Mês" estão de acordo com os valores recebidos da lista |
| **E** nenhuma linha tem valor recebido maior que o valor a receber sem explicação |

| **Critérios de aceitação** |
| :------------------------- |
| Os totais e os valores recebidos da listagem são coerentes entre si. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** As linhas somam R$ 499,50 (igual a "Entradas"), mas "Recebido no Mês" mostra R$ 475,00 com "100,00% recebido". A conta 1608 (Lila) tem R$ 75,50 a receber e R$ 100,00 recebido. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V11) |
