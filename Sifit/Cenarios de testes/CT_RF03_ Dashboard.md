## Cenário 03: Dashboard (gráficos e Inteligência Sifit).

### Caso de Teste 01: Abrir a página Dashboard.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C03-CT01 | A página Dashboard abre com o título e o caminho de navegação corretos. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                  |
| :---------------------------------------------------------- |
| **DADO** que estamos na página inicial                      |
| **QUANDO** clicamos em "Dashboard" no menu lateral          |
| **ENTÃO** a rota `/dash` abre                               |
| **E** o título e o caminho de navegação mostram "Dashboard" |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O título da página e o caminho de navegação são "Dashboard". |

| **Resultado da execução**                                                                                                                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O topo mostra "Início > Despesas Fixas" e o título "Despesas Fixas", enquanto o conteúdo é o do Dashboard. Em 28/10/2026, no Sifit Unialfa, o caso falhou: a rota `/dash` abre, mas o título e o caminho de navegação mostram "Despesas Fixas". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/fbc8ddfc-e244-413c-995b-c8bee8733105) |

---

### Caso de Teste 02: Conferir os títulos dos gráficos.

| ID       | Descrição                                                                                                            |
| :------- | :------------------------------------------------------------------------------------------------------------------- |
| C03-CT02 | Os blocos de gráficos (Clientes, Matrículas, Contas a Receber, Cancelamentos e Avaliações) mostram títulos legíveis. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que estamos na página Dashboard                                          |
| **QUANDO** rolamos a página até os gráficos                                       |
| **ENTÃO** os títulos de cada bloco e de cada gráfico estão legíveis no tema Claro |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| Todos os títulos dos gráficos podem ser lidos sem esforço. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** Os títulos (por exemplo "Clientes", "Matrículas", "Frequência", "Idade", "Sexo") aparecem em cor muito próxima à do fundo e quase não dá para ler. Em 28/10/2026, no Sifit Unialfa, o caso falhou: os títulos dos gráficos (por exemplo "Frequência", "Idade", "Sexo") e os títulos de bloco ("Clientes", "Matrículas") aparecem em cor escura ou branca sobre fundo de cor parecida e quase não dá para ler. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/72ff4074-832d-451e-908c-674402829bf3) |

---

### Caso de Teste 03: Conferir os alunos em risco entre as telas.

| ID       | Descrição                                                                                                |
| :------- | :------------------------------------------------------------------------------------------------------- |
| C03-CT03 | A quantidade de alunos em risco é a mesma na Página Inicial, na Inteligência de Retenção e no Dashboard. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                  |
| :---------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na Página Inicial                                                                      |
| **E** anotamos o valor do card "alunos em risco de evasão" e os totais de risco da Inteligência de Retenção |
| **QUANDO** abrimos o Dashboard e olhamos "Alunos em risco"                                                  |
| **ENTÃO** os três valores indicam a mesma quantidade de alunos em risco                                     |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| A quantidade de alunos em risco não muda de uma tela para outra. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** Em 28/10/2026: Página Inicial mostra "1 alunos em risco de evasão"; Inteligência de Retenção mostra 0 alto, 4 médio e 0 baixo; Dashboard mostra "0 Alunos em risco". Em 28/10/2026, no Sifit Unialfa, o caso falhou: página Inicial: "1 alunos em risco de evasão". Inteligência de Retenção: 0 alto risco, 4 médio risco, 0 baixo risco. Dashboard: "0 Alunos em risco". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a0888ff3-82b8-458c-afb0-b9aecdd5df18) |

---

### Caso de Teste 04: Acesso à Inteligência pelo Dashboard.

| ID       | Descrição                                                                                   |
| :------- | :------------------------------------------------------------------------------------------ |
| C03-CT04 | Verificar se o botão "Ver Inteligência" direciona para os resultados da Inteligência Sifit. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                      |
| :------------------------------------------------------------------------------ |
| **DADO** que estamos na tela do Dashboard                                       |
| **QUANDO** clicarmos no botão "Ver Inteligência"                                |
| **ENTÃO** deveremos ser direcionados à tela de resultados da Inteligência Sifit |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O botão deve direcionar para a tela correta. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/22bac58d-c274-4627-ae30-d31c6db1182a) |
