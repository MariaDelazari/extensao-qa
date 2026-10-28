## Cenário 03: Dashboard (gráficos e Inteligência Sifit).

### Caso de Teste 01: Abrir a página Dashboard.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT01 | A página Dashboard abre com o título e o caminho de navegação corretos. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página inicial |
| **QUANDO** clicamos em "Dashboard" no menu lateral |
| **ENTÃO** a rota `/dash` abre |
| **E** o título e o caminho de navegação mostram "Dashboard" |

| **Critérios de aceitação** |
| :------------------------- |
| O título da página e o caminho de navegação são "Dashboard". |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A rota `/dash` abre, mas o título e o caminho de navegação mostram "Despesas Fixas". |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-012 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V01) |

---

### Caso de Teste 02: Conferir os títulos dos gráficos.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT02 | Os blocos de gráficos (Clientes, Matrículas, Contas a Receber, Cancelamentos e Avaliações) mostram títulos legíveis. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página Dashboard |
| **QUANDO** rolamos a página até os gráficos |
| **ENTÃO** os títulos de cada bloco e de cada gráfico estão legíveis no tema Claro |

| **Critérios de aceitação** |
| :------------------------- |
| Todos os títulos dos gráficos podem ser lidos sem esforço. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Os títulos dos gráficos (por exemplo "Frequência", "Idade", "Sexo") e os títulos de bloco ("Clientes", "Matrículas") aparecem em cor escura ou branca sobre fundo de cor parecida e quase não dá para ler. |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-013 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V02) |

---

### Caso de Teste 03: Conferir os alunos em risco entre as telas.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT03 | A quantidade de alunos em risco é a mesma na Página Inicial, na Inteligência de Retenção e no Dashboard. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos na Página Inicial |
| **E** anotamos o valor do card "alunos em risco de evasão" e os totais de risco da Inteligência de Retenção |
| **QUANDO** abrimos o Dashboard e olhamos "Alunos em risco" |
| **ENTÃO** os três valores indicam a mesma quantidade de alunos em risco |

| **Critérios de aceitação** |
| :------------------------- |
| A quantidade de alunos em risco não muda de uma tela para outra. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Página Inicial: "1 alunos em risco de evasão". Inteligência de Retenção: 0 alto risco, 4 médio risco, 0 baixo risco. Dashboard: "0 Alunos em risco". |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-014 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V03) |
