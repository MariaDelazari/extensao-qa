## Cenário 05: Gestão de matrículas.

### Caso de Teste 01: Abrir a listagem de matrículas.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT01 | A tela de matrículas mostra os indicadores e a listagem. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos autenticados |
| **QUANDO** clicamos em "Matrículas" no menu lateral |
| **ENTÃO** a tela mostra os indicadores (Matrículas Ativas, Recorrentes, Não Renovadas, Cadastradas este Mês) e a listagem com código, nome, plano e status |

| **Critérios de aceitação** |
| :------------------------- |
| A tela de matrículas abre com indicadores e listagem preenchidos. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** A tela abriu com os indicadores (3 ativas, 0 recorrentes, 60 não renovadas, 3 cadastradas no mês) e a listagem. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V09) |

---

### Caso de Teste 02: Cadastrar matrícula sem escolher o cliente.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT02 | A matrícula não é salva sem cliente. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em "Cadastrar Matrícula" (`/adicionar-matricula`) |
| **E** não escolhemos o cliente |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema avisa que o cliente precisa ser selecionado |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e mostra aviso sobre o cliente. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Selecione o cliente!" e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V09) |

---

### Caso de Teste 03: Conferir matrículas ativas com os clientes ativos.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT03 | As matrículas ativas pertencem a clientes ativos. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/matriculas` e anotamos as matrículas com status ATIVO |
| **QUANDO** abrimos `/clientes` com Status "Ativo" |
| **ENTÃO** os clientes das matrículas ativas aparecem como ativos |

| **Critérios de aceitação** |
| :------------------------- |
| A quantidade e os nomes dos clientes ativos batem com as matrículas ativas. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Matrículas tem 3 ativas (242 - Marcelo Longo Zandonadi, 241 - Rafaela Andrade, 240 - Lila). Clientes com Status "Ativo" mostra só 1 (408 - Lila); os cadastros de Marcelo Longo Zandonadi e Rafaela Andrade aparecem como INATIVO. |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-018 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V10) |
