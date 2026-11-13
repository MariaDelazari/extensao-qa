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

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 02: Busca de lead pelo nome.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C15-CT02 | Verificar se a busca pelo nome retorna os leads correspondentes. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem leads cadastrados. |

| **Passos**                                                                |
| :------------------------------------------------------------------------ |
| **DADO** que estamos na tela de prospecção                                |
| **QUANDO** informarmos "joão" no campo de busca                           |
| **ENTÃO** a listagem deverá exibir os leads "João Rabelo" e "João Coelho" |

| **Critérios de aceitação**                                                                 |
| :----------------------------------------------------------------------------------------- |
| O sistema deve filtrar os leads pelo nome, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 03: Busca de lead pelo telefone e pelo e-mail.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C15-CT03 | Verificar se a busca encontra o lead pelo telefone e pelo e-mail. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o lead "Lead Teste Ville". |

| **Passos**                                                                                               |
| :------------------------------------------------------------------------------------------------------- |
| **DADO** que existe o lead "Lead Teste Ville" com telefone (44) 99999-0000 e e-mail lead.ville@teste.com |
| **QUANDO** informarmos o telefone e, depois, parte do e-mail no campo de busca                           |
| **ENTÃO** a listagem deverá exibir o lead "Lead Teste Ville" nas duas buscas                             |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve encontrar o lead pelo telefone e pelo e-mail. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

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

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 05: Filtro de leads por estágio.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C15-CT05 | Verificar se o filtro "Estágio" exibe somente os leads do estágio selecionado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                  |
| :------------------------------------------------------------------------------------------ |
| **DADO** que estamos na tela de prospecção                                                  |
| **QUANDO** selecionarmos "Proposta" no filtro "Estágio"                                     |
| **ENTÃO** a listagem deverá exibir somente o lead "Teste A", que está no estágio "Proposta" |

| **Critérios de aceitação**                                |
| :-------------------------------------------------------- |
| O sistema deve filtrar os leads pelo estágio selecionado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

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

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

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

| **Resultado da execução**                                                                                                                                                                                                                                                                      |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 28/10/2026, no Sifit Unialfa, o caso falhou: nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. O BUG-026 está em revisão: a execução automatizada não captura o aviso nativo do navegador. |

| **Evidência(s)**               |
| :----------------------------- |
| [PENDENTE VÍDEO] (roteiro V20) |

---

### Caso de Teste 08: Cadastro de lead com e-mail inválido.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C15-CT08 | Verificar se o sistema impede o cadastro de lead com e-mail em formato inválido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Adicionar Lead"                        |
| **E** informamos o nome "Lead Teste Ville" e o e-mail "emailinvalido" |
| **QUANDO** clicarmos no botão "Salvar Lead"                           |
| **ENTÃO** o sistema deverá informar que o e-mail é inválido           |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que um e-mail válido seja informado. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

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
| **E** informamos o nome "Lead Teste Ville", o e-mail "lead.ville@teste.com", o telefone e a observação "Teste Ville Nunes"        |
| **QUANDO** clicarmos no botão "Salvar Lead"                                                                                       |
| **ENTÃO** o lead deverá constar na listagem como "Novo Contato" e os indicadores "Leads" e "Novos Contatos" deverão aumentar em 1 |

| **Critérios de aceitação**                                  |
| :---------------------------------------------------------- |
| O sistema deve cadastrar o lead e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

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

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 11: Alteração do estágio do lead.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C15-CT11 | Verificar se o nome e o estágio do lead podem ser alterados. |

| **Pré-condições**                                                     |
| :-------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o lead "Lead Teste Ville". |

| **Passos**                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Visualizar" do lead "Lead Teste Ville"                                                                       |
| **E** alteramos o nome para "Lead Teste Ville Editado" e o estágio para "Interessado"                                                  |
| **QUANDO** clicarmos no botão "Salvar Lead"                                                                                            |
| **ENTÃO** a listagem deverá exibir o lead com o novo nome e o estágio "Interessado", e o indicador "Interessados" deverá aumentar em 1 |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O sistema deve salvar as alterações e atualizar os indicadores. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |

---

### Caso de Teste 12: Exclusão de lead.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C15-CT12 | Verificar se o lead é excluído ao confirmar a exclusão. |

| **Pré-condições**                                                    |
| :------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir lead de teste cadastrado. |

| **Passos**                                                                                    |
| :-------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de prospecção                                                    |
| **E** clicamos no botão "Deletar" do lead "Lead Teste Ville Editado"                          |
| **QUANDO** confirmarmos a mensagem "Deseja deletar este lead?"                                |
| **ENTÃO** o lead não deverá mais constar na listagem e os indicadores deverão ser atualizados |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| O sistema deve solicitar confirmação e excluir o lead. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] |
