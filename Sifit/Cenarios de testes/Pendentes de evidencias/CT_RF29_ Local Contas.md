## Cenário 29: Local Contas na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela Local Contas pelo menu.

| ID       | Descrição                                         |
| :------- | :------------------------------------------------ |
| C29-CT01 | Verificar se a tela Local Contas aparece no menu. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                            |
| :---------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT            |
| **QUANDO** procurarmos "Local Contas" no menu lateral |
| **ENTÃO** deverá existir um item para a tela          |

| **Critérios de aceitação**                                    |
| :------------------------------------------------------------ |
| O sistema deve oferecer acesso à tela Local Contas pelo menu. |

| **Resultado da execução**                                                                                                                       |
| :---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Não há item no menu. A tela só abre pelo link (/local-contas), abre sem o menu lateral e o topo mostra o título "Fichas de Treino". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Listagem dos locais de contas.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C29-CT02 | Verificar se a tela exibe os locais de contas cadastrados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas |
| **QUANDO** a tela carregar                                                                          |
| **ENTÃO** deverão aparecer os locais cadastrados com código e nome                                  |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| O sistema deve listar os locais de contas cadastrados. |

| **Resultado da execução**                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tabela fica vazia, mas a API (GET /api/local-contas/1) devolve 4 locais: Caixa Academia, Caixa Muay Thai, Teste e Teste2. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 03: Botão "Adicionar Local".

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C29-CT03 | Verificar se o botão "Adicionar Local" abre o cadastro de local. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas |
| **QUANDO** clicarmos em "Adicionar Local"                                                           |
| **ENTÃO** deverá abrir o cadastro de local de contas                                                |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve abrir o cadastro ao clicar em "Adicionar Local". |

| **Resultado da execução**                                                        |
| :------------------------------------------------------------------------------- |
| **Falhou.** "Adicionar Local" aparece como texto solto e não faz nada ao clicar. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 04: Cadastro de local de contas.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C29-CT04 | Verificar se o formulário da tela cadastra um local de contas. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas                         |
| **E** preenchemos o formulário com código "99", nome "Local Teste Maria", status "Ativo", valor "150" e recorrência "1 Mês" |
| **QUANDO** clicarmos em "Salvar"                                                                                            |
| **ENTÃO** o local deverá ser salvo, aparecer na listagem e exibir uma mensagem de sucesso                                   |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve salvar o local de contas e exibi-lo na listagem. |

| **Resultado da execução**                                                                                                                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O formulário da tela é o de Despesas Fixas (título "Despesas Fixas", com valor e recorrência). Ao salvar, nenhuma mensagem aparece, o local não entra na listagem e o registro é gravado como despesa fixa (#20 em Despesas Fixas). O código digitado não é enviado. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Salvar o formulário vazio.

| ID       | Descrição                                                                         |
| :------- | :-------------------------------------------------------------------------------- |
| C29-CT05 | Verificar se o sistema avisa os campos obrigatórios ao salvar o formulário vazio. |

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

| **Resultado da execução**                                                                           |
| :-------------------------------------------------------------------------------------------------- |
| **Falhou.** Nenhuma mensagem aparece na tela. A API responde erro 500 ("Erro interno inesperado."). |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 06: Botão "Cancelar".

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C29-CT06 | Verificar se o botão "Cancelar" descarta o que foi digitado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                          |
| :-------------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a tela Local Contas pelo link https://sifitalfa.centrion.com.br/local-contas |
| **E** digitamos "Cancelar Teste" no campo Nome                                                      |
| **QUANDO** clicarmos em "Cancelar"                                                                  |
| **ENTÃO** os campos deverão ser limpos sem salvar nada                                              |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve descartar os dados digitados ao cancelar. |

| **Resultado da execução**                            |
| :--------------------------------------------------- |
| **Passou.** Os campos foram limpos e nada foi salvo. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |
