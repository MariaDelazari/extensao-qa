## Cenário 04: Gestão de clientes.

### Caso de Teste 01: Listar clientes e conferir a paginação.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT01 | A listagem de clientes mostra a paginação de acordo com o resultado do filtro. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/clientes` com o filtro Status "Ativo" (padrão) |
| **QUANDO** a listagem terminar de carregar |
| **ENTÃO** a tabela mostra os clientes ativos e o card "Clientes Ativos" tem a mesma quantidade |
| **E** a paginação só oferece as páginas que têm clientes |

| **Critérios de aceitação** |
| :------------------------- |
| A listagem e a paginação refletem o resultado do filtro aplicado. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A tabela mostra 1 cliente (408 - Lila) e o card "Clientes Ativos" mostra 1, mas a paginação oferece as páginas 1, 2 e 3. |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-016 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V05) |

---

### Caso de Teste 02: Buscar cliente pelo nome.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT02 | A busca por nome aceita parte do nome e não diferencia maiúsculas de minúsculas. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/clientes` com Status "Todos" |
| **E** digitamos "mar" no campo Nome |
| **QUANDO** clicamos em "Buscar" |
| **ENTÃO** a lista mostra só clientes cujo nome contém "mar" |
| **E** repetindo com "MAR" a lista tem a mesma quantidade |

| **Critérios de aceitação** |
| :------------------------- |
| A busca por nome filtra por parte do texto, sem diferenciar maiúsculas e minúsculas. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** "mar" e "MAR" retornaram 17 clientes cada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V06) |

---

### Caso de Teste 03: Buscar cliente pelo código.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT03 | A busca por código retorna o cliente com aquele código. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/clientes` com Status "Todos" |
| **E** digitamos "242" no campo Código |
| **QUANDO** clicamos em "Buscar" |
| **ENTÃO** a lista mostra só o cliente de código 242 |

| **Critérios de aceitação** |
| :------------------------- |
| A busca por código retorna apenas o cliente informado. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** A lista mostrou uma linha: 242 - Ricardo Ford. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V06) |

---

### Caso de Teste 04: Digitar letras no campo Código.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT04 | O campo Código da busca só aceita números. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em `/clientes` |
| **QUANDO** digitamos "abc" no campo Código |
| **ENTÃO** o campo não aceita as letras |

| **Critérios de aceitação** |
| :------------------------- |
| O campo Código recusa caracteres que não são números. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** O campo aceitou e manteve o texto "abc". |

| **Bug(s) relacionado(s)** |
| :------------------------ |
| BUG-017 |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V07) |

---

### Caso de Teste 05: Cadastrar cliente com campos obrigatórios vazios.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT05 | O cadastro de cliente não segue com os campos obrigatórios vazios. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos na tela "Cadastrar Cliente" (`/adicionar-cliente`) |
| **E** deixamos Nome, Sexo e Data de Nascimento vazios |
| **QUANDO** clicamos em "Cadastrar Cliente" |
| **ENTÃO** o sistema avisa que falta preencher e permanece na tela |

| **Critérios de aceitação** |
| :------------------------- |
| O cadastro é bloqueado e a tela informa o campo que falta. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** O sistema permaneceu em `/adicionar-cliente`, não enviou requisição e mostrou "Preencha o nome da pessoa". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V08) |
