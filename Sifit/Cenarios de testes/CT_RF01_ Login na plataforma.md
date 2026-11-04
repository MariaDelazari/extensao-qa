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

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** O login válido retornou erro 500 ou entrou com o nome "Jair" no lugar da conta de teste. Em 28/10/2026 o login com a senha atual entrou e a saudação mostrou "Jair". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/eff97211-a309-4a7e-b090-426a557268da) |

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

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Com senha incorreta, `POST /api/login` retornou 500 e a tela mostrou "Erro no servidor. Erro interno inesperado.", e não "O nome de usuário e senha não correspondem.". |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/37a1e688-e126-4bb3-989c-de2732780ce4) |

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

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Com os campos vazios, o login seguiu para a API sem aviso de campos obrigatórios. |

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

| **Resultado da execução** |
| :------------------------ |
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

| **Resultado da execução** |
| :------------------------ |
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

| **Resultado da execução** |
| :------------------------ |
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

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** O link "Esqueci minha senha" não saiu da tela de login. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/c647a93a-812e-418f-8f05-d080e188b70f) |

