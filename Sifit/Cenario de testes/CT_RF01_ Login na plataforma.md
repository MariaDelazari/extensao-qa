## Cenário 01: Login na plataforma.

### Caso de Teste 01: Login com credenciais válidas.

| ID       | Descrição                                                         |
| -------- | ----------------------------------------------------------------- |
| C01-CT01 | O login será realizado com o usuário e a senha da conta de teste. |

| **Pré-condições**                                              |
| -------------------------------------------------------------- |
| As credenciais fornecidas (usuário e senha) devem ser válidas. |

| **Passos**                                                          |
| ------------------------------------------------------------------- |
| **DADO** que estamos na página de login do Sifit                    |
| **E** preenchemos "marcelo_zandonadi" no campo Login                |
| **E** preenchemos a senha "12345678" válida da conta no campo Senha |
| **QUANDO** clicarmos no botão "Entrar"                              |
| **ENTÃO**  seremos redirecionados para o Dashboard do sistema       |

| **Critérios de aceitação**                                     |
| -------------------------------------------------------------- |
| O redirecionamento para o Dashboard deve ocorrer corretamente. |

| Evidencia(s)                                                    |
| --------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/eff97211-a309-4a7e-b090-426a557268da) |
