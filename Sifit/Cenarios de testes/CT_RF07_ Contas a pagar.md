## Cenário 07: Contas a pagar.

### Caso de Teste 01: Criar conta a pagar com campos vazios.

| ID       | Descrição |
| :------- | :-------- |
| C07-CT01 | A conta a pagar não é salva com os campos vazios e o sistema orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Conta" em `/contas-pagar` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em salvar |
| **ENTÃO** o sistema informa quais campos faltam, sem erro de servidor |

| **Critérios de aceitação** |
| :------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/cadastrar-conta-pagar/1` retornou 500 e a tela mostrou "Erro ao salvar conta a pagar". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V12) |
