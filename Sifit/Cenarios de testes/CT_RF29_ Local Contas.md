## Cenário 29: Local Contas na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Local Contas e listagem dos locais.

| ID       | Descrição                                                                                |
| :------- | :--------------------------------------------------------------------------------------- |
| C29-CT01 | Verificar se a tela Local Contas abre pelo menu e lista os locais de contas cadastrados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                |
| :---------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                |
| **QUANDO** procurarmos "Local Contas" no menu lateral                                     |
| **E** acessarmos a tela pelo link https://sifitalfa.centrion.com.br/local-contas          |
| **ENTÃO** a tela deverá ter item no menu e listar os locais cadastrados com código e nome |

| **Critérios de aceitação**                                                                |
| :---------------------------------------------------------------------------------------- |
| O sistema deve oferecer acesso à tela pelo menu e listar os locais de contas cadastrados. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                 |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. Pelo link, a tela abre sem o menu lateral, com o título "Fichas de Treino", e a tabela fica vazia, embora a API (GET /api/local-contas/1) devolva 4 locais: Caixa Academia, Caixa Muay Thai, Teste e Teste2. "Adicionar Local" aparece como texto solto, não como botão. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/0d22bc75-111d-4a8c-86b2-19839bd01ee2) |

---

### Caso de Teste 02: Cadastro pelo formulário da tela.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C29-CT02 | Verificar se o formulário da tela Local Contas salva o registro. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                               |
| :------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas      |
| **E** preenchemos o nome "teste local contas", o status "Ativo", a recorrência "1 Dia" e o valor "10,00" |
| **QUANDO** clicarmos em "Salvar"                                                                         |
| **ENTÃO** o registro deverá ser salvo, aparecer na listagem e exibir uma mensagem de sucesso             |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve salvar o local de contas e exibi-lo na listagem. |

| **Resultado da execução**                                                                                                                                                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O formulário da tela é o de Despesas Fixas (título "Despesas Fixas", com valor e recorrência) e chama a rota de despesa fixa (POST /api/cria/despesa-fixa/1), que responde erro 500 ("Erro interno inesperado."). A tela mostra "Erro ao deletar Despesa" e nada é salvo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a3ff71fa-45ae-4366-b766-436374566b88) |

---

### Caso de Teste 03: Salvar o formulário vazio.

| ID       | Descrição                                                                         |
| :------- | :-------------------------------------------------------------------------------- |
| C29-CT03 | Verificar se o sistema avisa os campos obrigatórios ao salvar o formulário vazio. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas |
| **E** não preenchemos nenhum campo                                                                  |
| **QUANDO** clicarmos em "Salvar"                                                                    |
| **ENTÃO** o sistema deverá avisar os campos obrigatórios e não salvar                               |

| **Critérios de aceitação**                                                         |
| :--------------------------------------------------------------------------------- |
| O sistema deve impedir o salvamento sem os campos obrigatórios, com aviso na tela. |

| **Resultado da execução**                                                                                                                |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O formulário é enviado sem aviso dos campos obrigatórios. A API responde erro 500 e a tela mostra "Erro ao deletar Despesa". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e6c2700e-1de9-4b9e-be87-ec2811c86df6) |

---

### Caso de Teste 04: Botão "Cancelar".

| ID       | Descrição                                       |
| :------- | :---------------------------------------------- |
| C29-CT04 | Verificar se o botão "Cancelar" não salva nada. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas |
| **QUANDO** clicarmos em "Cancelar"                                                                  |
| **ENTÃO** nada deverá ser salvo                                                                     |

| **Critérios de aceitação**                  |
| :------------------------------------------ |
| O sistema não deve salvar nada ao cancelar. |

| **Resultado da execução**                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Ao clicar em "Cancelar", nenhuma requisição é enviada (DevTools) e nada é salvo. O formulário continua na tela. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/88cc8c8b-023b-41f9-a6ad-4f4e69304922) |
