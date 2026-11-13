## Cenário 05: Gestão de planos na plataforma SIFIT.

### Caso de Teste 01: Acesso à listagem de planos.

| ID       | Descrição                                                                                       |
| :------- | :---------------------------------------------------------------------------------------------- |
| C05-CT01 | Verificar se a tela de planos é exibida com os filtros, os indicadores, o ranking e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                 |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                 |
| **QUANDO** acessarmos o menu "Planos"                                                                                                                      |
| **ENTÃO** a tela deverá exibir os filtros de busca, os indicadores (Planos, Ativos, Alunos em Planos e Receita Estimada), o ranking e a listagem de planos |

| **Critérios de aceitação**                                                                    |
| :-------------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de planos com todos os seus componentes carregados corretamente. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f218079a-29e4-4378-9d5c-2c7b75b45d6a) |

---

### Caso de Teste 02: Exibição da quantidade de alunos e da receita dos planos.

| ID       | Descrição                                                                                                 |
| :------- | :-------------------------------------------------------------------------------------------------------- |
| C05-CT02 | Verificar se a coluna "Alunos", o ranking e o indicador "Receita Estimada" refletem as matrículas ativas. |

| **Pré-condições**                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem matrículas ativas (ex.: plano "Treino Livre", R$ 52,00, com 1 aluno). |

| **Passos**                                                                                                                                                                  |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de planos                                                                                                                                      |
| **QUANDO** observarmos a coluna "Alunos" do plano "Treino Livre", o ranking e o indicador "Receita Estimada"                                                                |
| **ENTÃO** a coluna "Alunos" do plano "Treino Livre" deverá exibir 1 aluno, o ranking deverá exibir a mensalidade de R$ 52,00 e a receita estimada deverá ser maior que zero |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| Os indicadores, o ranking e a listagem devem apresentar valores consistentes com as matrículas ativas. |

| **Resultado da execução**                                                                                         |
| :---------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A coluna "Alunos" exibe 0, a receita estimada exibe R$ 0,00 e a mensalidade no ranking exibe R$ 0,00. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a5ed20f9-d1e4-4e37-90ce-9941e6799792) |

---

### Caso de Teste 03: Busca de plano pelo nome.

| ID       | Descrição                                                                                     |
| :------- | :-------------------------------------------------------------------------------------------- |
| C05-CT03 | Verificar se a busca pelo nome retorna os planos correspondentes, inclusive com nome parcial. |

| **Pré-condições**                                                                  |
| :--------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir plano cadastrado com o nome pesquisado. |

| **Passos**                                                                     |
| :----------------------------------------------------------------------------- |
| **DADO** que estamos na tela de planos                                         |
| **E** informamos "plano" no campo "Nome do plano"                              |
| **QUANDO** clicarmos no botão "Buscar"                                         |
| **ENTÃO** a listagem deverá exibir apenas os planos que contêm "Plano" no nome |

| **Critérios de aceitação**                                                                             |
| :----------------------------------------------------------------------------------------------------- |
| O sistema deve filtrar a listagem pelo nome informado, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/2f7b2993-8c8c-4cd8-9c40-6fa55c8cbff4) |

---

### Caso de Teste 04: Busca de plano pelo código.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C05-CT04 | Verificar se a busca pelo código retorna somente o plano com o código informado. |

| **Pré-condições**                                                                    |
| :----------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir plano cadastrado com o código pesquisado. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos na tela de planos                          |
| **E** informamos "1" no campo "Código"                          |
| **QUANDO** clicarmos no botão "Buscar"                          |
| **ENTÃO** a listagem deverá exibir somente o plano de código #1 |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| O sistema deve retornar apenas o plano cujo código é igual ao informado. |

| **Resultado da execução**                                      |
| :------------------------------------------------------------- |
| **Falhou.** O sistema exibe os planos #1, #11, #16, #41 e #51. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/ec3ca053-5d62-438d-aa52-034d12e49b9a) |

---

### Caso de Teste 05: Cadastro de plano sem grupo.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C05-CT05 | Verificar se o sistema valida o campo "Grupo" antes de salvar o plano. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Plano"                        |
| **E** informamos apenas o nome "Plano Teste Ville"                    |
| **QUANDO** clicarmos no botão "Salvar Plano"                          |
| **ENTÃO** o sistema deverá informar que o campo "Grupo" é obrigatório |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| O sistema deve validar o grupo e exibir uma mensagem clara, sem erro interno. |

| **Resultado da execução**                                                                                                                                                                                                                                            |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O sistema exibe "Erro ao salvar plano" e a API retorna erro 500 com a instrução SQL que falhou. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso falhou: modal genérico "Erro ao salvar plano"; o console mostra HTTP 500. O Grupo não é sinalizado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/fa85a065-f8b6-45aa-989b-d65a05e2eb66) |

---

### Caso de Teste 06: Cadastro de plano com quantidade de parcelas negativa.

| ID       | Descrição                                                                              |
| :------- | :------------------------------------------------------------------------------------- |
| C05-CT06 | Verificar se o sistema impede o cadastro de plano com quantidade de parcelas negativa. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Plano"                              |
| **E** informamos o nome "Plano Teste Ville Negativo" e um grupo             |
| **E** informamos "-3" no campo "Parcelas"                                   |
| **QUANDO** clicarmos no botão "Salvar Plano"                                |
| **ENTÃO** o sistema deverá informar que a quantidade de parcelas é inválida |

| **Critérios de aceitação**                                            |
| :-------------------------------------------------------------------- |
| O sistema deve aceitar somente quantidade de parcelas maior que zero. |

| **Resultado da execução**                           |
| :-------------------------------------------------- |
| **Falhou.** O plano é cadastrado com "-3" parcelas. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/1a785e1d-5f84-4b11-9c13-50be1961a7f4) |

---

### Caso de Teste 07: Cadastro de plano com dados válidos.

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C05-CT07 | Verificar se o plano é cadastrado ao informar todos os dados corretamente. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                |
| :-------------------------------------------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Plano"                                                            |
| **E** informamos o nome "Plano Teste Ville", o grupo "Treino Livre" e a cobrança "Mensalidade recorrente" |
| **E** informamos 1 parcela, valor mensal de R$ 99,90 e valor de matrícula de R$ 10,00                     |
| **QUANDO** clicarmos no botão "Salvar Plano"                                                              |
| **ENTÃO** o plano deverá constar na listagem com status "ATIVO" e valor R$ 99,90                          |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve cadastrar o plano e exibi-lo na listagem. |

| **Resultado da execução**                                                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: plano listado (R$ 99,90, Mensalidade, ATIVO). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/eefb8181-d14f-4432-9e98-512757143e14) |

---

### Caso de Teste 08: Alteração dos dados do plano.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C05-CT08 | Verificar se as alterações nos dados do plano são salvas corretamente. |

| **Pré-condições**                                            |
| :----------------------------------------------------------- |
| O usuário deve estar autenticado e existir plano cadastrado. |

| **Passos**                                                                             |
| :------------------------------------------------------------------------------------- |
| **DADO** que estamos visualizando o plano "Plano Teste Ville"                          |
| **E** alteramos o nome para "Plano Teste Ville Editado" e o valor mensal para R$ 89,90 |
| **QUANDO** clicarmos no botão "Salvar Plano"                                           |
| **ENTÃO** a listagem deverá exibir o nome e o valor atualizados                        |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| O sistema deve salvar as alterações e exibi-las na listagem. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/5491b725-464d-49bb-b928-edcbf1a40056) |

---

### Caso de Teste 09: Inativação do plano.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C05-CT09 | Verificar se o plano é inativado ao alterar o seu status para "Inativo". |

| **Pré-condições**                                       |
| :------------------------------------------------------ |
| O usuário deve estar autenticado e existir plano ativo. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos visualizando o plano "Plano Teste Ville Editado" |
| **E** selecionamos "Inativo" no campo "Status"                        |
| **QUANDO** clicarmos no botão "Salvar Plano"                          |
| **ENTÃO** o plano deverá constar com status "INATIVO" na listagem     |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| O sistema deve atualizar o status do plano para inativo. |

| **Resultado da execução**                         |
| :------------------------------------------------ |
| **Falhou.** O plano permanece com status "ATIVO". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/9f76f60c-600d-4c55-b9ae-8eb8069889e9) |

---

### Caso de Teste 10: Plano inativo indisponível para matrícula.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C05-CT10 | Verificar se planos inativos não são exibidos como opção no cadastro de matrícula. |

| **Pré-condições**                                                                          |
| :----------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem planos inativos (ex.: "AVA" e "Teste Final"). |

| **Passos**                                                                         |
| :--------------------------------------------------------------------------------- |
| **DADO** que existem planos com status "INATIVO"                                   |
| **QUANDO** acessarmos a tela "Cadastrar Matrícula" e abrirmos o campo "Modalidade" |
| **ENTÃO** somente os planos ativos deverão ser exibidos                            |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| O sistema não deve permitir matricular clientes em planos inativos. |

| **Resultado da execução**                                                                                                                                                                                        |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Os planos inativos "AVA" e "Teste Final" são exibidos como opção. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso falhou: planos com status INATIVO aparecem na lista e podem ser selecionados. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/96013002-d0e4-4057-8dc1-383ef6437707) |

---

### Caso de Teste 11: Exclusão de plano.

| ID       | Descrição                                                |
| :------- | :------------------------------------------------------- |
| C05-CT11 | Verificar se o plano é excluído ao confirmar a exclusão. |

| **Pré-condições**                                                         |
| :------------------------------------------------------------------------ |
| O usuário deve estar autenticado e existir plano sem alunos matriculados. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que estamos na tela de planos                                      |
| **E** clicamos no botão "Deletar" (X) do plano "Plano Teste Ville Negativo" |
| **QUANDO** confirmarmos a mensagem "Deseja deletar o Plano?"                |
| **ENTÃO** o plano não deverá mais constar na listagem                       |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema deve solicitar confirmação e excluir o plano. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/10a1fc37-182b-4eac-9caf-2300fbd8aa54) |

---

### Caso de Teste 12: Cadastro de plano com o formulário vazio.

| ID       | Descrição                                                                      |
| :------- | :----------------------------------------------------------------------------- |
| C05-CT12 | Verificar se o sistema impede o cadastro de plano sem nenhum campo preenchido. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que abrimos o formulário "Novo Plano"                          |
| **QUANDO** clicarmos no botão "Salvar Plano" sem preencher nenhum campo |
| **ENTÃO** o campo "Nome" deverá ser sinalizado como obrigatório         |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O cadastro deve ser bloqueado e o campo obrigatório informado. |

| **Resultado da execução**                                                                                                                                                                                                                                                     |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Validação do navegador exibida no campo Nome. Em 28/10/2026, no Sifit Unialfa, o caso falhou: nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. O BUG-025 está em revisão: a execução automatizada não captura o aviso nativo do navegador. |

| **Evidência(s)**                    |
| :---------------------------------- |
| [Print](../Evidencias/C05-CT12.png) |

---

### Caso de Teste 13: Cadastro de plano com valor mensal negativo.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C05-CT13 | Verificar se o campo "Valor Mensal" recusa valores negativos. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                              |
| :------------------------------------------------------ |
| **DADO** que abrimos o formulário "Novo Plano"          |
| **QUANDO** digitarmos "-50" no campo "Valor Mensal"     |
| **ENTÃO** o sistema não deverá aceitar o valor negativo |

| **Critérios de aceitação**                       |
| :----------------------------------------------- |
| O sinal negativo deve ser ignorado ou rejeitado. |

| **Resultado da execução**                                     |
| :------------------------------------------------------------ |
| **Passou.** A máscara ignorou o sinal "-" (campo ficou 0,50). |

| **Evidência(s)**                    |
| :---------------------------------- |
| [Print](../Evidencias/C05-CT13.png) |

---

### Caso de Teste 14: Filtro de planos pelo status "Inativo".

| ID       | Descrição                                                                  |
| :------- | :------------------------------------------------------------------------- |
| C05-CT14 | Verificar se o filtro "Status" em "Inativo" lista somente planos inativos. |

| **Pré-condições**                                                      |
| :--------------------------------------------------------------------- |
| O usuário deve estar autenticado e existirem planos ativos e inativos. |

| **Passos**                                             |
| :----------------------------------------------------- |
| **DADO** que estamos na listagem de planos             |
| **E** selecionamos "Inativo" no filtro "Status"        |
| **QUANDO** clicarmos no botão "Buscar"                 |
| **ENTÃO** somente planos inativos deverão ser listados |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| A listagem deve exibir apenas planos inativos. |

| **Resultado da execução**                                                                                |
| :------------------------------------------------------------------------------------------------------- |
| **Passou.** Somente planos INATIVOS listados; quantidade coerente com o total de planos menos os ativos. |

| **Evidência(s)**                    |
| :---------------------------------- |
| [Print](../Evidencias/C05-CT14.png) |
