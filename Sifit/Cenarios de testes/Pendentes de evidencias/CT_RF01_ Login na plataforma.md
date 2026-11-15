## Cenário 01: Login na plataforma.

### Caso de Teste 01: Login com credenciais válidas.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C01-CT01 | O login será realizado com o usuário e a senha da conta de teste. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| As credenciais fornecidas (usuário e senha) devem ser válidas. |

| **Passos**                                                          |
| :------------------------------------------------------------------ |
| **DADO** que estamos na página de login do Sifit                    |
| **E** preenchemos "marcelo_zandonadi" no campo Login                |
| **E** preenchemos a senha "12345678" válida da conta no campo Senha |
| **QUANDO** clicarmos no botão "Entrar"                              |
| **ENTÃO** seremos redirecionados para o Dashboard do sistema        |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| O redirecionamento para o Dashboard deve ocorrer corretamente. |

| **Resultado da execução**                                                                                                                                                                                                                                                                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O login válido mostrou "Erro no servidor" ou entrou com o nome "Jair" no lugar da conta de teste. Em 28/10/2026 o login com a senha atual entrou e a saudação mostrou "Jair". Em outra execução, o caso passou. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso passou: redirecionado para /dashboard com a mensagem "Boa noite, (nome do usuário)!". |

| **Evidência(s)**                      |
| :------------------------------------ |
| [Vídeo](coloque o link do video aqui) |

---

### Caso de Teste 02: Tentativa de login com senha incorreta.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C01-CT02 | O login falhará quando a senha não corresponder ao usuário. |

| **Pré-condições**                                                                    |
| :----------------------------------------------------------------------------------- |
| O usuário marcelo_zandonadi existe. O navegador está na página de login, sem sessão. |

| **Passos**                                                                                                |
| :-------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit                                                          |
| **E** preenchemos "marcelo_zandonadi" no campo Login                                                      |
| **E** preenchemos "senhaerrada" no campo Senha                                                            |
| **QUANDO** clicarmos no botão "Entrar"                                                                    |
| **ENTÃO** permaneceremos em `/login` e será exibido o texto "O nome de usuário e senha não correspondem." |

| **Critérios de aceitação**                                                                         |
| :------------------------------------------------------------------------------------------------- |
| A mensagem "O nome de usuário e senha não correspondem." fica visível e a página inicial não abre. |

| **Resultado da execução**                                                                                                                                                              |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** Com a senha incorreta, a tela mostrou "Erro no servidor. Erro interno inesperado.", e não "O nome de usuário e senha não correspondem.". Em outra execução, o caso passou. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/a6cbb545-f415-4e44-b446-20f146f32a1c) |

---

### Caso de Teste 03: Tentativa de login com campos obrigatórios vazios.

| ID       | Descrição                                                                     |
| :------- | :---------------------------------------------------------------------------- |
| C01-CT03 | O login não deve seguir quando os campos de usuário e senha estiverem vazios. |

| **Pré-condições**                                   |
| :-------------------------------------------------- |
| Nenhuma. A página de login está aberta, sem sessão. |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit                                               |
| **E** deixamos os campos Login e Senha vazios                                                  |
| **QUANDO** clicarmos no botão "Entrar"                                                         |
| **ENTÃO** o sistema deve impedir a autenticação e informar que os dois campos são obrigatórios |

| **Critérios de aceitação**                                 |
| :--------------------------------------------------------- |
| A tela indica os campos que faltam e o Dashboard não abre. |

| **Resultado da execução**                                                                                                                                                                                                                                     |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Falhou.** Com os campos vazios, o login foi tentado sem nenhum aviso de campo obrigatório. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso falhou: a tela mostra "O nome de usuário e senha não correspondem."; não há validação de campo obrigatório. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/fcd3f7a9-9e1b-4aa3-a683-f5155d753e53) |

---

### Caso de Teste 04: Login com espaços extras nas credenciais válidas.

| ID       | Descrição                                                                        |
| :------- | :------------------------------------------------------------------------------- |
| C01-CT04 | Credenciais válidas com espaços no início ou no fim dos campos devem autenticar. |

| **Pré-condições**                                                                           |
| :------------------------------------------------------------------------------------------ |
| A conta de teste possui usuário e senha válidos. A página de login está aberta, sem sessão. |

| **Passos**                                                                         |
| :--------------------------------------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit                                   |
| **E** preenchemos um usuário válido com espaços no início ou no fim do campo Login |
| **E** preenchemos a senha válida com espaços no início ou no fim do campo Senha    |
| **QUANDO** clicarmos no botão "Entrar"                                             |
| **ENTÃO** seremos autenticados e redirecionados para o Dashboard                   |

| **Critérios de aceitação**                                                       |
| :------------------------------------------------------------------------------- |
| Espaços apenas nas pontas dos campos não impedem o login de credenciais válidas. |

| **Resultado da execução**                                                         |
| :-------------------------------------------------------------------------------- |
| **Falhou.** Com espaços nas pontas das credenciais válidas, o login foi recusado. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/51531b19-254b-468b-ad89-7487194fc22a) |

---

### Caso de Teste 05: Persistência da sessão com "Manter conectado".

| ID       | Descrição                                                                         |
| :------- | :-------------------------------------------------------------------------------- |
| C01-CT05 | Com "Manter conectado" marcado, a autenticação deve continuar ao voltar ao Sifit. |

| **Pré-condições**                                                                                          |
| :--------------------------------------------------------------------------------------------------------- |
| As credenciais da conta de teste são válidas. A opção "Manter conectado" está disponível na tela de login. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit                      |
| **E** preenchemos usuário e senha válidos                             |
| **E** marcamos a opção "Manter conectado"                             |
| **QUANDO** clicarmos em "Entrar" e abrirmos o Sifit novamente         |
| **ENTÃO** a sessão deve continuar, sem pedir as credenciais outra vez |

| **Critérios de aceitação**                           |
| :--------------------------------------------------- |
| Ao retornar ao sistema, o usuário segue autenticado. |

| **Resultado da execução**                                                     |
| :---------------------------------------------------------------------------- |
| **Falhou.** Com "Manter conectado", o retorno ao Sifit pediu o login de novo. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/0e862f82-e4d0-49df-9406-0ff970332873) |

---

### Caso de Teste 06: Acesso ao dashboard sem sessão válida.

| ID       | Descrição                                                                     |
| :------- | :---------------------------------------------------------------------------- |
| C01-CT06 | Sem sessão válida, o endereço `/dashboard` não deve abrir a área autenticada. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O navegador está na tela de login, sem sessão válida. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que estamos na tela de login, sem sessão válida              |
| **QUANDO** inserimos `/dashboard` na barra de endereços               |
| **ENTÃO** o sistema deve voltar para o login e não exibir o Dashboard |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| A área autenticada não abre pelo endereço direto quando não há sessão válida. |

| **Resultado da execução**                                    |
| :----------------------------------------------------------- |
| **Falhou.** O endereço `/dashboard` abriu sem sessão válida. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/0e862f82-e4d0-49df-9406-0ff970332873) |

---

### Caso de Teste 07: Acesso à recuperação de senha.

| ID       | Descrição                                                                |
| :------- | :----------------------------------------------------------------------- |
| C01-CT07 | O link "Esqueci minha senha" deve abrir o fluxo de recuperação de senha. |

| **Pré-condições**              |
| :----------------------------- |
| A página de login está aberta. |

| **Passos**                                            |
| :---------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit      |
| **E** localizamos o link "Esqueci minha senha"        |
| **QUANDO** clicarmos nesse link                       |
| **ENTÃO** o sistema deve abrir a recuperação de senha |

| **Critérios de aceitação**                                                         |
| :--------------------------------------------------------------------------------- |
| O clique tira o usuário da tela de login e entra no fluxo de recuperação de senha. |

| **Resultado da execução**                                                                                                                                               |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** O link "Esqueci minha senha" não saiu da tela de login. Em 23 a 24/10/2026, no sifit.centrion.com.br, o caso falhou: nada acontece; o link aponta para "#". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

---

### Caso de Teste 08: Tentativa de acesso com usuário inexistente.

| ID       | Descrição                                                                            |
| :------- | :----------------------------------------------------------------------------------- |
| C01-CT08 | Verificar se o sistema impede o acesso quando é informado um usuário não cadastrado. |

| **Pré-condições** |
| :---------------- |
| Nenhuma.          |

| **Passos**                                                                                     |
| :--------------------------------------------------------------------------------------------- |
| **DADO** que acessamos a página de login do SIFIT                                              |
| **E** informamos o usuário "usuario_inexistente_qa"                                            |
| **E** informamos a senha "senhaerrada"                                                         |
| **QUANDO** clicarmos no botão "Entrar"                                                         |
| **ENTÃO** o sistema deverá apresentar uma mensagem informando que as credenciais são inválidas |

| **Critérios de aceitação**                                                                    |
| :-------------------------------------------------------------------------------------------- |
| O sistema deve negar o acesso, exibir a mensagem de erro e manter o usuário na tela de login. |

| **Resultado da execução**                                                     |
| :---------------------------------------------------------------------------- |
| **Passou.** Exibida a mensagem "O nome de usuário e senha não correspondem.". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/461b0484-4a78-4535-81d5-c3542770ff27) |

---

### Caso de Teste 09: Logout e acesso a tela interna.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C01-CT09 | Verificar se, após sair do sistema, as telas internas deixam de ser acessíveis. |

| **Pré-condições**                                     |
| :---------------------------------------------------- |
| O usuário deve estar autenticado na plataforma SIFIT. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos autenticados no SIFIT                      |
| **E** abrimos o menu do usuário e clicamos em "Sair do sistema" |
| **QUANDO** acessarmos diretamente o endereço /clientes          |
| **ENTÃO** deveremos ser direcionados à tela de login            |

| **Critérios de aceitação**                                               |
| :----------------------------------------------------------------------- |
| A sessão deve ser encerrada e as telas internas devem exigir novo login. |

| **Resultado da execução**                                 |
| :-------------------------------------------------------- |
| **Passou.** Redirecionado para /login nas duas situações. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/06bd8930-85a1-4de6-8889-eb73d57b799d) |
