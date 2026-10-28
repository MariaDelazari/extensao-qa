## Cenário 10: Avaliações físicas.

### Caso de Teste 01: Cadastrar avaliação sem escolher o aluno.

| ID       | Descrição |
| :------- | :-------- |
| C10-CT01 | A avaliação não é salva sem aluno. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Cadastrar Avaliação" em `/avaliacoes` |
| **E** não escolhemos o aluno |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema pede para selecionar um aluno |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e mostra aviso sobre o aluno. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Selecione um aluno." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V16) |
