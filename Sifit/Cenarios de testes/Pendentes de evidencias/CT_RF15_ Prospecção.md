## Cenário 15: Prospecção de leads na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de prospecção.

| ID       | Descrição                                                                                                           |
| :------- | :------------------------------------------------------------------------------------------------------------------ |
| C15-CT01 | Verificar se a tela de prospecção é exibida com a busca, o filtro de estágio, os indicadores e a listagem de leads. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                              |
| :-------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                              |
| **QUANDO** acessarmos o menu "Prospecção"                                                                                               |
| **ENTÃO** a tela deverá exibir a busca, o filtro "Estágio", os indicadores (Leads, Novos Contatos e Interessados) e a listagem de leads |

| **Critérios de aceitação**                                                           |
| :----------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de prospecção com todos os seus componentes carregados. |

| **Resultado da execução**                                                                                                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A tela abriu com a busca "Nome, e-mail, telefone ou código", o filtro "Estágio", os botões "Limpar" e "Adicionar Lead", os indicadores (Leads 6, Novos Contatos 2, Interessados 2) e a listagem de leads. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a4b29552-e468-43d4-a17e-0ef80e7914b5) |

---

### Caso de Teste 02: Busca de lead pelo nome.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C15-CT02 | Verificar se a busca pelo nome retorna os leads correspondentes. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem os leads "Maria Teste". |

| **Passos**                                                   |
| :----------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                   |
| **QUANDO** informarmos "Maria" no campo de busca             |
| **ENTÃO** a listagem deverá exibir só os leads "Maria Teste" |

| **Critérios de aceitação**                                                                 |
| :----------------------------------------------------------------------------------------- |
| O sistema deve filtrar os leads pelo nome, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                                       |
| :---------------------------------------------------------------------------------------------- |
| **Passou.** Com "Maria" na busca, a listagem mostrou só os leads "Maria Teste" (códigos 8 e 9). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/552d263b-192b-4ff8-8e74-cb5ffe847d24) |

---

### Caso de Teste 03: Busca de lead pelo telefone.

| ID       | Descrição                                           |
| :------- | :-------------------------------------------------- |
| C15-CT03 | Verificar se a busca encontra o lead pelo telefone. |

| **Pré-condições**                                                                          |
| :----------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o lead "Teste Maria" com o telefone 4474005974. |

| **Passos**                                                                                 |
| :----------------------------------------------------------------------------------------- |
| **DADO** que copiamos o telefone "4474005974" na janela "Visualizar Lead" da "Teste Maria" |
| **QUANDO** colarmos o telefone no campo de busca                                           |
| **ENTÃO** a listagem deverá exibir só o lead "Teste Maria"                                 |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| O sistema deve encontrar o lead pelo telefone. |

| **Resultado da execução**                                                                           |
| :-------------------------------------------------------------------------------------------------- |
| **Passou.** Com o telefone "4474005974" na busca, a listagem mostrou só a "Teste Maria" (código 1). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/824d6a8a-afa7-42d9-abaf-cd62e7af4bcd) |

---

### Caso de Teste 04: Busca de lead inexistente.

| ID       | Descrição                                                      |
| :------- | :------------------------------------------------------------- |
| C15-CT04 | Verificar se o sistema informa que nenhum lead foi encontrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                                 |
| **QUANDO** informarmos um nome inexistente no campo de busca               |
| **ENTÃO** o sistema deverá apresentar a mensagem "Nenhum lead encontrado." |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa quando a busca não retornar resultados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 05: Filtro de leads por estágio.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C15-CT05 | Verificar se o filtro "Estágio" exibe somente os leads do estágio selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                 |
| :--------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                                                                 |
| **QUANDO** selecionarmos "Proposta" no filtro "Estágio"                                                    |
| **ENTÃO** a listagem deverá exibir somente o lead "Maria Teste" (código 9), que está no estágio "Proposta" |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve filtrar os leads pelo estágio selecionado. |

| **Resultado da execução**                                                                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O filtro "Proposta" mostrou só o lead 9 e o "Novo Contato" só o lead 8; "Interessado", "Fez Aula Experimental" e "Fechado" mostraram "Nenhum lead encontrado.". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/b9896da9-7a57-477c-b2d7-98a81ca5653d) |

---

### Caso de Teste 06: Limpar busca e filtros.

| ID       | Descrição                                              |
| :------- | :----------------------------------------------------- |
| C15-CT06 | Verificar se o botão "Limpar" remove a busca aplicada. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que informamos um texto no campo de busca                                |
| **QUANDO** clicarmos no botão "Limpar"                                            |
| **ENTÃO** o campo de busca deverá ser limpo e todos os leads deverão ser exibidos |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve remover os filtros e exibir a listagem completa. |

| **Resultado da execução**                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Com "Maria" na busca e um estágio no filtro, o botão "Limpar" limpou a busca, voltou o filtro para "Todos" e a listagem mostrou todos os leads. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/552d263b-192b-4ff8-8e74-cb5ffe847d24) |

---

### Caso de Teste 07: Cadastro de lead sem nome.

| ID       | Descrição                                                  |
| :------- | :--------------------------------------------------------- |
| C15-CT07 | Verificar se o sistema impede o cadastro de lead sem nome. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                            |
| :------------------------------------------------------------------------------------ |
| **DADO** que abrimos a janela "Adicionar Lead"                                        |
| **E** mantemos o campo "Nome completo" vazio                                          |
| **QUANDO** clicarmos no botão "Salvar Lead"                                           |
| **ENTÃO** o sistema deverá solicitar o preenchimento do nome ("Preencha este campo.") |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o nome seja informado. |

| **Resultado da execução**                                                                                                                 |
| :---------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Ao clicar em "Salvar Lead" com o nome vazio, o navegador mostrou "Preencha este campo." no campo Nome e o lead não foi salvo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/be15afd3-1f5d-487e-97b0-a2dbe4dbe192) |

---

### Caso de Teste 08: Cadastro de lead com e-mail inválido.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C15-CT08 | Verificar se o sistema impede o cadastro de lead com e-mail em formato inválido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                  |
| :---------------------------------------------------------- |
| **DADO** que abrimos a janela "Adicionar Lead"              |
| **E** informamos o nome "teste" e o e-mail "dasda"          |
| **QUANDO** clicarmos no botão "Salvar Lead"                 |
| **ENTÃO** o sistema deverá informar que o e-mail é inválido |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que um e-mail válido seja informado. |

| **Resultado da execução**                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O navegador mostrou "Inclua um "@" no endereço de e-mail. "dasda" está com um "@" faltando." e o lead não foi salvo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/56ef8c16-8929-4811-a413-144bb3d1f7f0) |

---

### Caso de Teste 09: Cadastro de lead com dados válidos.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C15-CT09 | Verificar se o lead é cadastrado e os indicadores são atualizados. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                        |
| :-------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Adicionar Lead"                                                                                    |
| **E** informamos o nome "Maria Teste" e mantemos o estágio "Novo Contato"                                                         |
| **QUANDO** clicarmos no botão "Salvar Lead"                                                                                       |
| **ENTÃO** o lead deverá constar na listagem como "Novo Contato" e os indicadores "Leads" e "Novos Contatos" deverão aumentar em 1 |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O sistema deve cadastrar o lead e atualizar os indicadores. |

| **Resultado da execução**                                                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O lead "Maria Teste" apareceu na listagem como "Novo Contato" (resposta 200), e os indicadores Leads e Novos Contatos passaram de 6 para 7 e de 2 para 3. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/be15afd3-1f5d-487e-97b0-a2dbe4dbe192) |

---

### Caso de Teste 10: Cadastro de lead duplicado.

| ID       | Descrição                                                                                            |
| :------- | :--------------------------------------------------------------------------------------------------- |
| C15-CT10 | Verificar se o sistema impede o cadastro de lead com o mesmo e-mail e telefone de um lead existente. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o lead "Lead Teste Ville". |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que o lead "Lead Teste Ville" já está cadastrado                            |
| **E** abrimos a janela "Adicionar Lead" e informamos o mesmo nome, e-mail e telefone |
| **QUANDO** clicarmos no botão "Salvar Lead"                                          |
| **ENTÃO** o sistema deverá informar que já existe um lead com esses dados            |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| O sistema não deve permitir leads duplicados. |

| **Resultado da execução**                       |
| :---------------------------------------------- |
| **Falhou.** O lead é cadastrado em duplicidade. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 11: Alteração do estágio do lead.

| ID       | Descrição                                         |
| :------- | :------------------------------------------------ |
| C15-CT11 | Verificar se o estágio do lead pode ser alterado. |

| **Pré-condições**                                                                                     |
| :---------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o lead "Maria Teste" (código 8) no estágio "Novo Contato". |

| **Passos**                                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos na lupa (Visualizar) do lead "Maria Teste"                                                      |
| **E** alteramos o estágio para "Interessado"                                                                          |
| **QUANDO** clicarmos no botão "Salvar Lead"                                                                           |
| **ENTÃO** a listagem deverá exibir o lead no estágio "Interessado", e o indicador "Interessados" deverá aumentar em 1 |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve salvar as alterações e atualizar os indicadores. |

| **Resultado da execução**                                                                                                                                                              |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A janela "Visualizar Lead" abriu com os dados do lead; ao salvar (resposta 200), o lead passou a "Interessado", Novos Contatos foi de 1 para 0 e Interessados de 0 para 1. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e788dfb6-76f9-4cb2-a990-19c0300176c6) |

---

### Caso de Teste 12: Exclusão de lead.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C15-CT12 | Verificar se o lead é excluído ao confirmar a exclusão. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem leads cadastrados. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                                                    |
| **E** clicamos no "X" (excluir) de um lead                                                    |
| **QUANDO** confirmarmos a exclusão no botão "Confirmar"                                       |
| **ENTÃO** o lead não deverá mais constar na listagem e os indicadores deverão ser atualizados |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| O sistema deve solicitar confirmação e excluir o lead. |

| **Resultado da execução**                                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Ao confirmar, o lead saiu da listagem e os indicadores foram atualizados (Leads de 8 para 7 na primeira exclusão); a gravação exclui 6 leads e a lista termina com Leads 2. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ee6f43d1-b3ca-42b0-8e96-8e91ec6c1938) |


---

### Caso de Teste 13: Cadastro de lead com telefone com letras.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C15-CT13 | Verificar se o campo Telefone do lead aceita apenas números. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                               |
| :----------------------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Adicionar Lead"                                                                           |
| **E** informamos o nome "Maria Teste", o estágio "Proposta", o e-mail "mariateste@gmail.com" e o telefone "6asdasdasdad" |
| **QUANDO** clicarmos no botão "Salvar Lead"                                                                              |
| **ENTÃO** o sistema deverá recusar o telefone com letras e informar o formato correto                                    |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| O campo Telefone aceita apenas números no formato (00) 00000-0000. |

| **Resultado da execução**                                                                                                      |
| :----------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O lead foi salvo com o telefone "6asdasdasdad" (resposta 200) e "Visualizar Lead" mostra o telefone com as letras. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3b272b31-fdc0-4818-a515-351268d7aa8e) |

---

### Caso de Teste 14: Busca de lead pelo código.

| ID       | Descrição                                         |
| :------- | :------------------------------------------------ |
| C15-CT14 | Verificar se a busca encontra o lead pelo código. |

| **Pré-condições**                                                                                   |
| :-------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem os leads de código 1 ("Teste Maria") e 2 ("joazinho"). |

| **Passos**                                                       |
| :--------------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                       |
| **QUANDO** informarmos "1" e, depois, "2" no campo de busca      |
| **ENTÃO** a listagem deverá exibir só o lead do código informado |
| **E** o botão "Limpar" deverá trazer de volta todos os leads     |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O sistema deve encontrar o lead pelo código. |

| **Resultado da execução**                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** Com "1" a listagem mostrou só a "Teste Maria", com "2" só o "joazinho", e o "Limpar" trouxe os dois de volta. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/8eb37367-15ff-4e43-a4f8-9d65509b5a73) |
