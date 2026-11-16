## Cenário 30: Bancos e Banco Recorrente na plataforma SIFIT.

### Caso de Teste 01: Acesso às telas de bancos pelo menu.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C30-CT01 | Verificar se as telas Bancos e Banco Recorrente aparecem no menu. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                           |
| :------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                           |
| **QUANDO** procurarmos "Bancos" e "Banco Recorrente" no menu lateral |
| **ENTÃO** deverá existir um item para cada tela                      |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve oferecer acesso às telas de bancos pelo menu. |

| **Resultado da execução**                                                                                                     |
| :---------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. As telas só abrem pelo link (/bancos e /banco-recorrente), e Bancos abre sem o menu lateral. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a7570689-c2c4-46f2-b064-c9b9a0030a0b) |

---

### Caso de Teste 02: Listagem de bancos.

| ID       | Descrição                                        |
| :------- | :----------------------------------------------- |
| C30-CT02 | Verificar se a tela exibe os bancos cadastrados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **QUANDO** a tela carregar                                                              |
| **ENTÃO** deverão aparecer os bancos cadastrados com os botões de visualizar e excluir  |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O sistema deve listar os bancos cadastrados. |

| **Resultado da execução**                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Foram listados os bancos cadastrados (Banco Brasil, Itaú, Bradesco, Banco Inter, Banco Cora, Nubank, C6 e os bancos de teste) com os botões de visualizar e excluir. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2576259f-63af-411c-9435-1dce2b60d290) |

---

### Caso de Teste 03: Salvar banco vazio.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C30-CT03 | Verificar se o sistema impede salvar banco sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **E** deixamos os campos vazios                                                         |
| **QUANDO** clicarmos em "Salvar"                                                        |
| **ENTÃO** o sistema deverá avisar que o nome é obrigatório                              |

| **Critérios de aceitação**                |
| :---------------------------------------- |
| O sistema não deve salvar banco sem nome. |

| **Resultado da execução**                                                      |
| :----------------------------------------------------------------------------- |
| **Falhou.** Nenhuma mensagem aparece e um banco sem nome é criado na listagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/76f082bc-40ee-47db-aaeb-0d181408c68c) |

---

### Caso de Teste 04: Cadastro de banco.

| ID       | Descrição                          |
| :------- | :--------------------------------- |
| C30-CT04 | Verificar se o banco é cadastrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **E** informamos o nome "Banco Teste Ville" e o código do banco "999"                   |
| **QUANDO** clicarmos em "Salvar"                                                        |
| **ENTÃO** o banco deverá aparecer na listagem                                           |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve cadastrar o banco e exibi-lo na listagem. |

| **Resultado da execução**                                     |
| :------------------------------------------------------------ |
| **Passou.** O banco "Banco Teste Ville" apareceu na listagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1b0bcc7e-9c4b-4845-b9d4-f05aafc34a54) |

---

### Caso de Teste 05: Cadastro de banco duplicado.

| ID       | Descrição                                     |
| :------- | :-------------------------------------------- |
| C30-CT05 | Verificar se o sistema impede banco repetido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |
| Deve existir o banco "Banco Teste Ville".             |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **E** informamos de novo o nome "Banco Teste Ville" e o código "999"                    |
| **QUANDO** clicarmos em "Salvar"                                                        |
| **ENTÃO** o sistema deverá avisar que o banco já existe                                 |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O sistema não deve cadastrar banco repetido. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Falhou.** O banco é cadastrado de novo e aparece duas vezes na listagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f1723af8-3f46-4586-8c15-340990fd857a) |

---

### Caso de Teste 06: Alteração de banco.

| ID       | Descrição                               |
| :------- | :-------------------------------------- |
| C30-CT06 | Verificar se o banco pode ser alterado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |
| Deve existir o banco "Banco Teste Ville".             |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **E** clicamos na lupa do banco "Banco Teste Ville"                                     |
| **E** alteramos o nome para "Banco Teste Ville Editado"                                 |
| **QUANDO** clicarmos em "Salvar"                                                        |
| **ENTÃO** a listagem deverá mostrar o nome novo                                         |

| **Critérios de aceitação**                  |
| :------------------------------------------ |
| O sistema deve salvar a alteração do banco. |

| **Resultado da execução**                                            |
| :------------------------------------------------------------------- |
| **Passou.** A listagem passou a mostrar "Banco Teste Ville Editado". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/65c7c968-e7cc-4f61-aa24-8453061baea5) |

---

### Caso de Teste 07: Exclusão de banco.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C30-CT07 | Verificar se o banco é excluído após a confirmação. |

| **Pré-condições**                                                                                         |
| :-------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT.                                                     |
| Atenção: ao confirmar, o sistema tenta excluir o tipo de pagamento com o mesmo código do banco (BUG-129). |

| **Passos**                                                                              |
| :-------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Bancos pelo link https://sifitalfa.centrion.com.br/bancos |
| **QUANDO** clicarmos no X do banco "Banco Brasil"                                       |
| **E** clicarmos em "Confirmar"                                                          |
| **ENTÃO** a confirmação deverá falar do banco e o banco deverá ser excluído             |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve confirmar e excluir somente o banco escolhido. |

| **Resultado da execução**                                                                                                                                                                                                                |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A confirmação pergunta "Deseja deletar o Tipo de Pagamento?". Ao confirmar, aparece "Erro ao deletar tipo de pagamento" e o banco continua na listagem. A tela envia o código do banco para a exclusão de tipo de pagamento. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/6849358c-8f8d-44ce-96f5-e1ae38ec4006) |
