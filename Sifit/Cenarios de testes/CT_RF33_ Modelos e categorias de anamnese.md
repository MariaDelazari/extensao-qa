## Cenário 33: Modelos e categorias de anamnese na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de categorias de anamnese.

| ID       | Descrição                                                                                              |
| :------- | :----------------------------------------------------------------------------------------------------- |
| C33-CT01 | Verificar se a tela de categorias de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                                                 |
| **QUANDO** clicarmos em "Categorias" no grupo Saúde do menu lateral                                                                                                                                                        |
| **ENTÃO** a tela "Categorias de Anamnese" deverá abrir com a busca "Buscar categoria...", o filtro de status, o botão "Nova Categoria", os indicadores Total, Ativas, Inativas e Com perguntas e as categorias cadastradas |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A tela de categorias abre pelo menu com todos os seus componentes. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                                                                              |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A tela abriu em `/anamnese/categorias` com a busca, o filtro "Todos os status", o botão "Nova Categoria", os indicadores (Total 3, Ativas 3, Inativas 0, Com perguntas 3) e as categorias em cartões. O filtro "Ativo" mostrou as 3 categorias e o "Inativo" mostrou "Nenhuma categoria encontrada". Ao passar o mouse no cartão aparecem os ícones de editar (lápis) e excluir (lixeira). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/02ba0e96-2464-40cb-b20f-1a134cd9f29c) |

---

### Caso de Teste 02: Salvar categoria com o formulário vazio.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C33-CT02 | Verificar se o sistema impede o cadastro de categoria sem nome. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Categoria"                                         |
| **E** deixamos o campo "Nome da Categoria" vazio                                  |
| **QUANDO** tentarmos clicar em "Criar Categoria"                                  |
| **ENTÃO** o botão deverá ficar desabilitado e nenhuma categoria deverá ser criada |

| **Critérios de aceitação**                                           |
| :------------------------------------------------------------------- |
| A categoria não é salva sem nome e o campo aparece como obrigatório. |

| **Resultado da execução**                                                                                                                                                      |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O campo "Nome da Categoria" tem o asterisco de obrigatório e o botão "Criar Categoria" fica desabilitado enquanto o nome está vazio; nenhuma requisição é enviada. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/105c0f2a-ad01-45d9-a450-57416e589849) |

---

### Caso de Teste 03: Cadastro de categoria com dados válidos.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT03 | Verificar se a categoria é salva e aparece na listagem. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                                               |
| :------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Nova Categoria"                                                                |
| **E** informamos o nome "Objetivos", o ícone "bi-person-arms-up", a cor verde (#059669) e o status Ativo |
| **QUANDO** clicarmos no botão "Criar Categoria"                                                          |
| **ENTÃO** a categoria deverá aparecer na listagem e os indicadores Total e Ativas deverão aumentar em 1  |

| **Critérios de aceitação**                                         |
| :----------------------------------------------------------------- |
| A categoria é salva com os dados informados e aparece na listagem. |

| **Resultado da execução**                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A categoria "Objetivos" apareceu na listagem com o ícone e a cor escolhidos (resposta 201), e os indicadores Total e Ativas passaram de 3 para 4. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/af41c04d-af50-455c-9e5c-b7c779dc710b) |

---

### Caso de Teste 04: Indicador "Com perguntas" das categorias.

| ID       | Descrição                                                                          |
| :------- | :--------------------------------------------------------------------------------- |
| C33-CT04 | Verificar se o indicador "Com perguntas" conta só as categorias que têm perguntas. |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Ter acabado de cadastrar a categoria "Objetivos" (C33-CT03), que ainda não tem nenhuma pergunta. |

| **Passos**                                                              |
| :---------------------------------------------------------------------- |
| **DADO** que o indicador "Com perguntas" mostra 3 antes do cadastro     |
| **QUANDO** cadastrarmos a categoria "Objetivos", sem pergunta vinculada |
| **ENTÃO** o indicador "Com perguntas" deverá continuar em 3             |

| **Critérios de aceitação**                                                     |
| :----------------------------------------------------------------------------- |
| O indicador "Com perguntas" não muda ao cadastrar uma categoria sem perguntas. |

| **Resultado da execução**                                                                                                                                         |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O indicador "Com perguntas" passou de 3 para 4 junto com o Total. Ele mostra a quantidade total de categorias, e não as categorias que têm perguntas. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/af41c04d-af50-455c-9e5c-b7c779dc710b) |

---

### Caso de Teste 05: Cadastro de categoria duplicada.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C33-CT05 | Verificar se o sistema impede cadastrar duas categorias com o mesmo nome. |

| **Pré-condições**                                                                                                                                                  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Categorias de Anamnese" está aberta. |

| **Passos**                                                                         |
| :--------------------------------------------------------------------------------- |
| **DADO** que cadastramos a categoria "Teste Maria"                                 |
| **E** clicamos de novo em "Nova Categoria" e informamos o mesmo nome "Teste Maria" |
| **QUANDO** clicarmos no botão "Criar Categoria"                                    |
| **ENTÃO** o sistema deverá informar que a categoria já existe e não salvar outra   |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| O sistema não permite duas categorias com o mesmo nome. |

| **Resultado da execução**                                                                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** As duas "Teste Maria" foram salvas sem nenhum aviso (resposta 201 nas duas) e a listagem passou a mostrar duas categorias com o mesmo nome (Total de 4 para 6). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/d4c4a693-3fe8-44ac-b617-4176f81de4d0) |

---

### Caso de Teste 06: Busca de categoria pelo nome.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C33-CT06 | Verificar se a busca e o filtro de status filtram as categorias. |

| **Pré-condições**                                               |
| :-------------------------------------------------------------- |
| Existirem as categorias "Teste Maria", cadastradas no C33-CT05. |

| **Passos**                                                                                                        |
| :---------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Categorias de Anamnese"                                                             |
| **QUANDO** digitarmos "Teste Maria" no campo "Buscar categoria..." e trocarmos o filtro entre "Inativo" e "Ativo" |
| **ENTÃO** a listagem deverá mostrar só as categorias com "Teste Maria" no nome que tenham o status escolhido      |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| A busca e o filtro mostram apenas as categorias que correspondem. |

| **Resultado da execução**                                                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** Com "Teste Maria" na busca, a listagem mostrou só as duas "Teste Maria"; com o filtro "Inativo" apareceu "Nenhuma categoria encontrada" e com o "Ativo" as duas voltaram. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/44909f01-10ed-43c8-b565-77559b0a7751) |

---

### Caso de Teste 07: Alteração de categoria.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C33-CT07 | Verificar se a categoria pode ser alterada e inativada. |

| **Pré-condições**                  |
| :--------------------------------- |
| Existir a categoria "Teste Maria". |

| **Passos**                                                                                                     |
| :------------------------------------------------------------------------------------------------------------- |
| **DADO** que passamos o mouse no cartão "Teste Maria" e clicamos no ícone de lápis (Editar)                    |
| **E** alteramos o status para Inativo na janela "Editar Categoria"                                             |
| **QUANDO** clicarmos no botão "Atualizar"                                                                      |
| **ENTÃO** a categoria deverá aparecer como Inativo, e os indicadores Ativas e Inativas deverão ser atualizados |

| **Critérios de aceitação**                                   |
| :----------------------------------------------------------- |
| A alteração é salva e aparece na listagem e nos indicadores. |

| **Resultado da execução**                                                                                                                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A janela "Editar Categoria" abriu com os dados da categoria; ao clicar em "Atualizar" (resposta 200), Ativas passou de 6 para 5, Inativas de 0 para 1, e no filtro "Inativo" a categoria aparece como Inativo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/99b79383-50f5-4a53-b707-5722c8658e3d) |

---

### Caso de Teste 08: Exclusão de categoria.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C33-CT08 | Verificar se a categoria é excluída ao confirmar a exclusão. |

| **Pré-condições**                      |
| :------------------------------------- |
| Existirem as categorias "Teste Maria". |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que passamos o mouse no cartão "Teste Maria" e clicamos no ícone de lixeira (Excluir) |
| **QUANDO** confirmarmos a mensagem "Excluir a categoria "Teste Maria"?" no botão "Confirmar"   |
| **ENTÃO** a categoria deverá sair da listagem e o indicador Total deverá diminuir em 1         |

| **Critérios de aceitação**                         |
| :------------------------------------------------- |
| A categoria é excluída somente após a confirmação. |

| **Resultado da execução**                                                                                                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** Ao confirmar, a "Teste Maria" ativa saiu da listagem (Total de 6 para 5) e, no filtro "Inativo", a outra "Teste Maria" também foi excluída (Total de 5 para 4); as duas exclusões responderam 200. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/e79b5845-246e-4a83-bd5a-adda3a735018) |

---

### Caso de Teste 09: Acesso à tela de modelos de anamnese.

| ID       | Descrição                                                                                           |
| :------- | :-------------------------------------------------------------------------------------------------- |
| C33-CT09 | Verificar se a tela de modelos de anamnese abre pelo menu com a busca, os indicadores e a listagem. |

| **Pré-condições**                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                                                                                       |
| **QUANDO** clicarmos em "Modelos" no grupo Saúde do menu lateral                                                                                                                                                                 |
| **ENTÃO** a tela "Modelos de Anamnese" deverá abrir com a busca "Buscar modelo...", o filtro de status, o botão "Novo Modelo", os indicadores Total de modelos, Ativos, Média de perguntas e Aplicações e os modelos cadastrados |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| A tela de modelos abre pelo menu com todos os seus componentes. |

| **Resultado da execução**                                                                                                                                                                                                                                |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A tela abriu em `/anamnese/modelos` com a busca, o filtro de status, o botão "Novo Modelo", os indicadores (Total de modelos 3, Ativos 2, Média de perguntas 1, Aplicações 15) e os cartões dos modelos com "Editar", "Preview" e a lixeira. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/461eb955-aa5a-442f-869f-14f66e9916de) |

---

### Caso de Teste 10: Salvar modelo sem nome.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C33-CT10 | Verificar se o sistema impede o cadastro de modelo sem nome. |

| **Pré-condições**                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A tela "Modelos de Anamnese" está aberta. |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo"                                        |
| **E** deixamos o campo "Nome do Modelo" vazio                                 |
| **QUANDO** tentarmos clicar em "Salvar Modelo"                                |
| **ENTÃO** o botão deverá ficar desabilitado e nenhum modelo deverá ser criado |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O modelo não é salvo sem nome e o campo aparece como obrigatório. |

| **Resultado da execução**                                                                                                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** "Novo Modelo" abriu a página "Novo Modelo de Anamnese" (`/anamnese/modelos/novo`); com o nome vazio, o botão "Salvar Modelo" fica desabilitado e o campo "Nome do Modelo" tem o asterisco de obrigatório. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/4c7b3ed2-4921-4d6c-a25c-11bb71834727) |

---

### Caso de Teste 11: Cadastro de modelo sem perguntas.

| ID       | Descrição                                                       |
| :------- | :-------------------------------------------------------------- |
| C33-CT11 | Verificar se o sistema exige pelo menos uma pergunta no modelo. |

| **Pré-condições**                                                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O usuário deve estar autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. A página "Novo Modelo de Anamnese" está aberta. |

| **Passos**                                                                                       |
| :----------------------------------------------------------------------------------------------- |
| **DADO** que informamos o nome "Cardio"                                                          |
| **E** não adicionamos nenhuma pergunta ao modelo                                                 |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                    |
| **ENTÃO** o sistema deverá informar que o modelo precisa de pelo menos uma pergunta e não salvar |

| **Critérios de aceitação**          |
| :---------------------------------- |
| O modelo não é salvo sem perguntas. |

| **Resultado da execução**                                                                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O botão "Salvar Modelo" foi liberado só com o nome e o modelo "Cardio" foi salvo (resposta 201), aparecendo na lista com "0 perguntas" (Total de 3 para 4). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/4c7b3ed2-4921-4d6c-a25c-11bb71834727) |

---

### Caso de Teste 12: Cadastro de modelo com pergunta obrigatória.

| ID       | Descrição                                                                              |
| :------- | :------------------------------------------------------------------------------------- |
| C33-CT12 | Verificar se o modelo é salvo com as perguntas escolhidas e a marcação de obrigatória. |

| **Pré-condições**                             |
| :-------------------------------------------- |
| Existirem perguntas em Perguntas de anamnese. |

| **Passos**                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------ |
| **DADO** que clicamos em "Novo Modelo"                                                                              |
| **E** informamos o nome e a descrição "Teste de MOdelo de Anamnese"                                                 |
| **E** clicamos no "+" das 3 perguntas disponíveis e marcamos "Obrigatória" em "Qual é o nome da academia"           |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                                       |
| **ENTÃO** o modelo deverá aparecer na listagem com 3 perguntas, e o indicador Total de modelos deverá aumentar em 1 |

| **Critérios de aceitação**                    |
| :-------------------------------------------- |
| O modelo é salvo com as perguntas escolhidas. |

| **Resultado da execução**                                                                                                                                                                             |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O "Resumo do Modelo" mostrou 3 perguntas, 1 obrigatória e 2 opcionais; ao salvar (resposta 201), o modelo apareceu na listagem com "3 perguntas" e o Total de modelos passou de 4 para 5. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3e474a32-d535-4cd2-b81d-2991c422973a) |

---

### Caso de Teste 13: Cadastro de modelo só com perguntas opcionais.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C33-CT13 | Verificar se o modelo pode ser salvo com todas as perguntas opcionais. |

| **Pré-condições**                             |
| :-------------------------------------------- |
| Existirem perguntas em Perguntas de anamnese. |

| **Passos**                                                                                         |
| :------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Novo Modelo" e informamos o nome e a descrição "Novo Modelo de Anamnese" |
| **E** clicamos no "+" das 3 perguntas disponíveis sem marcar "Obrigatória"                         |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                                      |
| **ENTÃO** o modelo deverá aparecer na listagem com 3 perguntas                                     |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O modelo é salvo com as perguntas opcionais. |

| **Resultado da execução**                                                                                                                          |
| :------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** O resumo mostrou 3 perguntas, 0 obrigatórias e 3 opcionais; ao salvar (resposta 201), o modelo apareceu na listagem com "3 perguntas". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/850e1502-88c6-49af-aee6-90d8fddd849d) |

---

### Caso de Teste 14: Pergunta obrigatória na edição do modelo.

| ID       | Descrição                                                                   |
| :------- | :-------------------------------------------------------------------------- |
| C33-CT14 | Verificar se a edição do modelo mostra a pergunta marcada como obrigatória. |

| **Pré-condições**                                                                                       |
| :------------------------------------------------------------------------------------------------------ |
| Existir o modelo "Teste de Pergunta Obrigatoria", criado com as 3 perguntas marcadas como obrigatórias. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Modelos de Anamnese"                         |
| **QUANDO** clicarmos em "Editar" no modelo "Teste de Pergunta Obrigatoria" |
| **ENTÃO** as 3 perguntas deverão aparecer com "Obrigatória" marcada        |

| **Critérios de aceitação**                               |
| :------------------------------------------------------- |
| A edição mostra a marcação de obrigatória que foi salva. |

| **Resultado da execução**                                                                                                                                                                                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O modelo foi criado com as 3 perguntas obrigatórias (resposta 201), mas a página "Editar Modelo" abriu com as 3 caixas "Obrigatória" desmarcadas, embora a API guarde "obrigatoria": "1". Ao salvar a edição (resposta 200), as perguntas deixaram de ser obrigatórias. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3f31d9eb-7fdc-4e40-8686-ca8ddb689fec) |

---

### Caso de Teste 15: Preview do modelo.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C33-CT15 | Verificar se o preview mostra as perguntas que o card do modelo informa. |

| **Pré-condições**                                                           |
| :-------------------------------------------------------------------------- |
| Existir o modelo "Teste de MOdelo de Anamnese", com 3 perguntas (C33-CT12). |

| **Passos**                                                                       |
| :------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Modelos de Anamnese"                               |
| **QUANDO** clicarmos em "Preview" no modelo "Teste de MOdelo de Anamnese"        |
| **ENTÃO** a janela deverá mostrar o nome, a descrição e as 3 perguntas do modelo |

| **Critérios de aceitação**                                                   |
| :--------------------------------------------------------------------------- |
| O preview lista a mesma quantidade de perguntas informada no card do modelo. |

| **Resultado da execução**                                                                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A janela mostrou o nome e a descrição do modelo e a mensagem "Nenhuma pergunta adicionada ainda.", embora o card informe "3 perguntas". O preview do "Manual SIFIT Anamnese Inicial" (1 pergunta) também fica vazio. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3e474a32-d535-4cd2-b81d-2991c422973a) |

---

### Caso de Teste 16: Aplicação com pergunta obrigatória sem resposta.

| ID       | Descrição                                                             |
| :------- | :-------------------------------------------------------------------- |
| C33-CT16 | Verificar se o assistente exige resposta para a pergunta obrigatória. |

| **Pré-condições**                                                                                                                |
| :------------------------------------------------------------------------------------------------------------------------------- |
| Existir o modelo "Teste de MOdelo de Anamnese" com a pergunta "Qual é o nome da academia" obrigatória e a cliente "Maria Teste". |

| **Passos**                                                                          |
| :---------------------------------------------------------------------------------- |
| **DADO** que estamos em Fichas Anamnese e clicamos em "Nova Anamnese"               |
| **E** selecionamos a aluna "Maria Teste" e o modelo "Teste de MOdelo de Anamnese"   |
| **QUANDO** deixarmos a pergunta obrigatória em branco e clicarmos em "Próxima"      |
| **ENTÃO** o sistema deverá impedir o avanço e informar que a pergunta é obrigatória |

| **Critérios de aceitação**                              |
| :------------------------------------------------------ |
| A anamnese não é finalizada sem a resposta obrigatória. |

| **Resultado da execução**                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O assistente avançou com a pergunta obrigatória em branco e a anamnese foi finalizada como concluída sem nenhuma resposta (resposta 201 com "respostas": []). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f0ee966a-4873-4846-a15c-b9d2adaedb07) |

---

### Caso de Teste 17: Aplicação de modelo com perguntas opcionais.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C33-CT17 | Verificar se a anamnese é finalizada com perguntas opcionais em branco. |

| **Pré-condições**                                                                                       |
| :------------------------------------------------------------------------------------------------------ |
| Existir o modelo "Novo Modelo de Anamnese" (3 perguntas opcionais, C33-CT13) e a cliente "Maria Teste". |

| **Passos**                                                                    |
| :---------------------------------------------------------------------------- |
| **DADO** que estamos em Fichas Anamnese e clicamos em "Nova Anamnese"         |
| **E** selecionamos a aluna "Maria Teste" e o modelo "Novo Modelo de Anamnese" |
| **E** respondemos só a primeira pergunta e deixamos as outras em branco       |
| **QUANDO** clicarmos em "Revisar" e em "Finalizar Anamnese"                   |
| **ENTÃO** a anamnese deverá ser salva com a resposta informada                |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| A anamnese é salva quando só perguntas opcionais ficam em branco. |

| **Resultado da execução**                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** A anamnese foi finalizada (resposta 201) com a resposta "Teste de perguntas NAO obrigatorias" na primeira pergunta. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/df41299a-c550-43ba-acba-cbea9979216f) |

---

### Caso de Teste 18: Busca e filtro de modelos.

| ID       | Descrição                                                     |
| :------- | :------------------------------------------------------------ |
| C33-CT18 | Verificar se a busca e o filtro de status filtram os modelos. |

| **Pré-condições**                             |
| :-------------------------------------------- |
| Existir o modelo "Cardio" com status Inativo. |

| **Passos**                                                                                               |
| :------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela "Modelos de Anamnese"                                                       |
| **QUANDO** digitarmos "Cardi" no campo "Buscar modelo..." e trocarmos o filtro entre "Inativo" e "Ativo" |
| **ENTÃO** a listagem deverá mostrar só os modelos com "Cardi" no nome que tenham o status escolhido      |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| A busca e o filtro mostram apenas os modelos que correspondem. |

| **Resultado da execução**                                                                                                                       |
| :---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A busca mostrou só o "Cardio"; com o filtro "Inativo" ele continuou aparecendo e com o "Ativo" apareceu "Nenhum modelo encontrado". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a9ea3105-d7df-4be5-a4b0-00285dde0872) |

---

### Caso de Teste 19: Alteração de modelo.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C33-CT19 | Verificar se o modelo pode ser alterado e inativado. |

| **Pré-condições**                     |
| :------------------------------------ |
| Existir o modelo "Cardio" (C33-CT11). |

| **Passos**                                                                        |
| :-------------------------------------------------------------------------------- |
| **DADO** que clicamos em "Editar" no modelo "Cardio"                              |
| **E** alteramos o status para Inativo                                             |
| **QUANDO** clicarmos no botão "Salvar Modelo"                                     |
| **ENTÃO** o modelo deverá aparecer como Inativo na listagem e no filtro "Inativo" |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| A alteração é salva e aparece na listagem. |

| **Resultado da execução**                                                                                                                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Passou.** A página "Editar Modelo" abriu com os dados do "Cardio"; ao salvar (resposta 200), o modelo voltou para a lista como Inativo, o indicador Ativos mostrou 2 e o filtro "Inativo" exibiu o "Cardio". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/aa805ed9-917d-4204-982e-47f1ec6e95f0) |

---

### Caso de Teste 20: Exclusão de modelo.

| ID       | Descrição                                                 |
| :------- | :-------------------------------------------------------- |
| C33-CT20 | Verificar se o modelo é excluído ao confirmar a exclusão. |

| **Pré-condições**                           |
| :------------------------------------------ |
| Existir o modelo "Novo Modelo de Anamnese". |

| **Passos**                                                                                            |
| :---------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no ícone de lixeira do modelo "Novo Modelo de Anamnese"                         |
| **QUANDO** confirmarmos a mensagem "Excluir o modelo "Novo Modelo de Anamnese"?" no botão "Confirmar" |
| **ENTÃO** o modelo deverá sair da listagem                                                            |

| **Critérios de aceitação**                      |
| :---------------------------------------------- |
| O modelo é excluído somente após a confirmação. |

| **Resultado da execução**                                                                                                                                           |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Passou.** Apareceu a mensagem "Excluir o modelo "Novo Modelo de Anamnese"?" com "Cancelar" e "Confirmar"; ao confirmar (resposta 200), o modelo saiu da listagem. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3b99f4b6-a0bd-4ea4-adda-e6aeac468e5e) |

---

### Caso de Teste 21: Exclusão de modelo já aplicado.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C33-CT21 | Verificar se o sistema impede excluir um modelo que já foi aplicado em anamnese. |

| **Pré-condições**                                                             |
| :---------------------------------------------------------------------------- |
| Existir o modelo "Teste de MOdelo de Anamnese" com "1 aplicações" (C33-CT16). |

| **Passos**                                                                                                |
| :-------------------------------------------------------------------------------------------------------- |
| **DADO** que clicamos no ícone de lixeira do modelo "Teste de MOdelo de Anamnese", que tem "1 aplicações" |
| **QUANDO** confirmarmos a exclusão                                                                        |
| **ENTÃO** o sistema deverá bloquear a exclusão ou oferecer apenas inativar o modelo                       |

| **Critérios de aceitação**            |
| :------------------------------------ |
| Um modelo já aplicado não é excluído. |

| **Resultado da execução**                                                                            |
| :--------------------------------------------------------------------------------------------------- |
| **Falhou.** O modelo foi excluído (resposta 200) mesmo já tendo sido aplicado à aluna "Maria Teste". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3b99f4b6-a0bd-4ea4-adda-e6aeac468e5e) |
