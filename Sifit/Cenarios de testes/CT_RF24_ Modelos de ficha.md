## Cenário 24: Modelos de ficha de treino na plataforma SIFIT.

### Caso de Teste 01: Acesso à tela de modelos de ficha.

| ID       | Descrição                                                                                      |
| :------- | :--------------------------------------------------------------------------------------------- |
| C24-CT01 | Verificar se a tela de modelos de ficha é exibida com os filtros, os indicadores e a listagem. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                                                                                                |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                                                                                                                |
| **QUANDO** acessarmos o menu "Modelo Ficha"                                                                                                               |
| **ENTÃO** a tela deverá exibir os filtros (Código, Título e Criador), os indicadores (Modelos, Criadores, Listados e Sem Criador) e a listagem de modelos |

| **Critérios de aceitação**                                                                 |
| :----------------------------------------------------------------------------------------- |
| O sistema deve exibir a tela de modelos de ficha com todos os seus componentes carregados. |

| **Resultado da execução**                                                  |
| :------------------------------------------------------------------------- |
| **Passou.** O sistema se comportou como descrito no critério de aceitação. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/8c15372c-42b7-4a72-8446-575dc0e3832c) |

---

### Caso de Teste 02: Busca de modelo pelo criador.

| ID       | Descrição                                                                     |
| :------- | :---------------------------------------------------------------------------- |
| C24-CT02 | Verificar se a busca pelo nome do criador retorna os modelos correspondentes. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| O usuário deve estar autenticado e existir modelo criado pela personal Gabriella. |

| **Passos**                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de modelos de ficha                                                                                 |
| **E** informamos "gab" no campo "Criador"                                                                                        |
| **QUANDO** clicarmos no botão de busca                                                                                           |
| **ENTÃO** a listagem deverá exibir somente os modelos da criadora "Gabriella" e o indicador "Listados" deverá acompanhar a busca |

| **Critérios de aceitação**                                                                      |
| :---------------------------------------------------------------------------------------------- |
| O sistema deve filtrar os modelos pelo criador, sem diferenciar letras maiúsculas e minúsculas. |

| **Resultado da execução**                                                        |
| :------------------------------------------------------------------------------- |
| **Passou.** A listagem exibiu somente o modelo de "Gabriella" e "1 registro(s)". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/cc68070f-6346-44e5-a153-9a7b02a98c7c) |

---

### Caso de Teste 03: Busca de modelo pelo código.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C24-CT03 | Verificar se a busca pelo código retorna o modelo correspondente. |

| **Pré-condições**                                                |
| :--------------------------------------------------------------- |
| O usuário deve estar autenticado e existir o modelo de código 2. |

| **Passos**                                             |
| :----------------------------------------------------- |
| **DADO** que estamos na tela de modelos de ficha       |
| **E** informamos "2" no campo "Código"                 |
| **QUANDO** clicarmos no botão de busca                 |
| **ENTÃO** a listagem deverá exibir somente o modelo #2 |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| O sistema deve filtrar os modelos pelo código. |

| **Resultado da execução**                                            |
| :------------------------------------------------------------------- |
| **Passou.** A listagem exibiu somente o modelo #2 e "1 registro(s)". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/fd9f32a9-65ec-462f-8efd-a75a4cea0fba) |

---

### Caso de Teste 04: Busca de modelo com código inexistente.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C24-CT04 | Verificar se o sistema informa que nenhum modelo foi encontrado. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                           |
| :------------------------------------------------------------------- |
| **DADO** que estamos na tela de modelos de ficha                     |
| **E** informamos "999" no campo "Código"                             |
| **QUANDO** clicarmos no botão de busca                               |
| **ENTÃO** o sistema deverá informar que nenhum modelo foi encontrado |

| **Critérios de aceitação**                                                             |
| :------------------------------------------------------------------------------------- |
| O sistema deve exibir uma mensagem informativa quando a busca não retornar resultados. |

| **Resultado da execução**                                                                                     |
| :------------------------------------------------------------------------------------------------------------ |
| **Passou.** A tela exibiu "Nenhum modelo de ficha encontrado", "0 registro(s)" e o indicador "Listados" em 0. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/3ccce354-1fec-4fee-9208-7f49f4df8755) |

---

### Caso de Teste 05: Criar modelo com o formulário vazio.

| ID       | Descrição                                      |
| :------- | :--------------------------------------------- |
| C24-CT05 | Verificar se o sistema exige o nome do modelo. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                   |
| :--------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Novo Modelo de Ficha" pelo botão "Nova Ficha" |
| **E** deixamos "Nome do Modelo" e "Personal" vazios                          |
| **QUANDO** clicarmos no botão "Criar Modelo"                                 |
| **ENTÃO** o sistema deverá apresentar o aviso "Informe o nome do modelo."    |

| **Critérios de aceitação**                                       |
| :--------------------------------------------------------------- |
| O sistema deve impedir o cadastro até que o nome seja informado. |

| **Resultado da execução**                                                           |
| :---------------------------------------------------------------------------------- |
| **Passou.** Apareceu o aviso "Informe o nome do modelo." e o modelo não foi criado. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/79127d51-5a1e-4d1f-b783-0641890aed82) |

---

### Caso de Teste 06: Criar modelo com dados válidos.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C24-CT06 | Verificar se o modelo de ficha é criado com nome e personal. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que abrimos a janela "Novo Modelo de Ficha"                                 |
| **E** informamos o nome "Modelo Teste Keltton" e selecionamos a personal "Gabriella" |
| **QUANDO** clicarmos no botão "Criar Modelo"                                         |
| **ENTÃO** o modelo deverá ser criado e constar na listagem                           |

| **Critérios de aceitação**         |
| :--------------------------------- |
| O modelo deve ser salvo e listado. |

| **Resultado da execução**                                                                                                                                                                                                             |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** A tela mostrou só "Erro ao salvar modelo." e o modelo não foi criado. No DevTools, o servidor responde "Escolha o objetivo do treino.", mas a janela não tem campo de objetivo. O mesmo ocorre sem selecionar a personal. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/f333fef6-b58e-44dc-b74d-2c57379d41ac) |

---

### Caso de Teste 07: Alteração de modelo de ficha.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C24-CT07 | Verificar se o botão "Alterar" abre o modelo escolhido. |

| **Pré-condições**                                       |
| :------------------------------------------------------ |
| O usuário deve estar autenticado e existir o modelo #1. |

| **Passos**                                               |
| :------------------------------------------------------- |
| **DADO** que estamos na tela de modelos de ficha         |
| **QUANDO** clicarmos no botão "Alterar" do modelo #1     |
| **ENTÃO** o sistema deverá abrir o modelo #1 para edição |

| **Critérios de aceitação**                     |
| :--------------------------------------------- |
| O botão "Alterar" deve abrir o próprio modelo. |

| **Resultado da execução**                                                                                                                         |
| :------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** O sistema abriu "/ficha-treino/alterar/1", a ficha de treino de um aluno ("Treino de Manual SIFIT Aluno Exemplo"), e não o modelo #1. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/b7528526-350e-4605-81b1-7036a6611c7b) |

---

### Caso de Teste 08: Cancelar a exclusão de modelo.

| ID       | Descrição                                            |
| :------- | :--------------------------------------------------- |
| C24-CT08 | Verificar se cancelar a confirmação mantém o modelo. |

| **Pré-condições**                                       |
| :------------------------------------------------------ |
| O usuário deve estar autenticado e existir o modelo #2. |

| **Passos**                                                                  |
| :-------------------------------------------------------------------------- |
| **DADO** que estamos na tela de modelos de ficha                            |
| **E** clicamos no botão "Deletar" do modelo #2                              |
| **QUANDO** clicarmos em "Cancelar" na mensagem "Deseja deletar esta ficha?" |
| **ENTÃO** o modelo deverá continuar na listagem                             |

| **Critérios de aceitação**                 |
| :----------------------------------------- |
| Nenhum dado deve ser excluído ao cancelar. |

| **Resultado da execução**                                                                                    |
| :----------------------------------------------------------------------------------------------------------- |
| **Passou.** A mensagem fechou, o modelo #2 continuou na listagem e nenhuma exclusão foi enviada ao servidor. |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](https://jam.dev/c/06c1d1cb-512b-465d-9edd-226a1ca3873a) |

---
