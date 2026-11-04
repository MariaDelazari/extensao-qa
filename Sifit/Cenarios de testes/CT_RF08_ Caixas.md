## Cenário 08: Caixas.

### Caso de Teste 01: Abrir caixa com campos vazios.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT01 | O caixa não é aberto com campos vazios e o sistema orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Abrir Caixa" em `/caixas` |
| **E** deixamos os campos sem preencher |
| **QUANDO** clicamos para confirmar a abertura |
| **ENTÃO** o sistema informa o que falta, sem erro de servidor |

| **Critérios de aceitação** |
| :------------------------- |
| Um aviso de campos obrigatórios é exibido e nenhum erro interno aparece. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/abrir-caixa/1` retornou 500 e a tela mostrou "Erro no servidor. Erro interno inesperado.". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V13) |
