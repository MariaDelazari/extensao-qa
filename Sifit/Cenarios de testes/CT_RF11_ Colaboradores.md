## Cenário 11: Colaboradores.

### Caso de Teste 01: Cadastrar colaborador com campos vazios.

| ID       | Descrição |
| :------- | :-------- |
| C11-CT01 | O colaborador não é salvo com os campos vazios e o sistema orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que estamos em "Novo Colaborador" (`/adicionar-colaborador`) |
| **E** deixamos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa os campos que faltam, sem erro de servidor |

| **Critérios de aceitação** |
| :------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/salvar/colaborador/1` retornou 500 e a tela mostrou "Erro no servidor. Erro interno inesperado.". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V17) |
