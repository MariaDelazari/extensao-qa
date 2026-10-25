## Cenário 04: Navegação pelos menus do sistema.

### Caso de Teste 01: Abrir os módulos do menu Principal.

| ID       | Descrição                                               |
| :------- | :------------------------------------------------------ |
| C04-CT01 | Check-in, Presenças e SifitBox abrem as próprias telas. |

| **Pré-condições**                  |
| :--------------------------------- |
| A conta de teste está autenticada. |

| **Passos**                                                            |
| :-------------------------------------------------------------------- |
| **DADO** que o menu PRINCIPAL está visível                            |
| **QUANDO** clicamos em Check-in                                       |
| **ENTÃO** a rota `/checkin` abre com o título Check-ins               |
| **QUANDO** clicamos em Presenças                                      |
| **ENTÃO** a rota `/presencas` abre com o título Presenças             |
| **QUANDO** clicamos em SifitBox                                       |
| **ENTÃO** a rota `/sifitbox/aulas` abre com o título SifitBox - Aulas |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| Os três itens saem do dashboard e abrem a tela do próprio módulo. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 02: Abrir os módulos de Operação da academia.

| ID       | Descrição                                                          |
| :------- | :----------------------------------------------------------------- |
| C04-CT02 | Clientes, matrículas, avaliações e contas abrem as próprias telas. |

| **Pré-condições**                  |
| :--------------------------------- |
| A conta de teste está autenticada. |

| **Passos**                                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------- |
| **DADO** que o menu OPERAÇÃO DA ACADEMIA está visível                                                                 |
| **QUANDO** clicamos em Clientes, Matrículas, Avaliações, Contas a Receber e Contas a Pagar, um por vez                |
| **ENTÃO** abrem, nesta ordem, as rotas `/clientes`, `/matriculas`, `/avaliacoes`, `/contas-receber` e `/contas-pagar` |
| **E** cada tela mostra o título do módulo                                                                             |

| **Critérios de aceitação**                                                    |
| :---------------------------------------------------------------------------- |
| Nenhum item de operação devolve para o login nem abre a tela de outro módulo. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 03: Abrir os módulos de Treinamento.

| ID       | Descrição                                              |
| :------- | :----------------------------------------------------- |
| C04-CT03 | Os itens de treino e de turma abrem as próprias telas. |

| **Pré-condições**                  |
| :--------------------------------- |
| A conta de teste está autenticada. |

| **Passos**                                                                                                                                                                        |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que o menu TREINAMENTO está visível                                                                                                                                      |
| **QUANDO** clicamos em Ficha de Treino, Exercícios, Grupos Musculares, Objetivos Treino, Grupos, Turmas, Categorias Crossfit e Box - Turmas                                       |
| **ENTÃO** abrem as rotas `/fichas-treino`, `/exercicios`, `/grupos-musculares`, `/objetivos-treino`, `/grupos`, `/turmas`, `/categorias-exercicios-crossfit` e `/sifitbox/turmas` |
| **E** cada tela mostra o título do módulo                                                                                                                                         |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| Os oito itens de treinamento abrem a própria listagem. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 04: Abrir os módulos Financeiro e Comercial.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C04-CT04 | Financeiro e comercial abrem as próprias telas, sem gravar lançamento. |

| **Pré-condições**                                                                 |
| :-------------------------------------------------------------------------------- |
| A conta de teste está autenticada. Nenhum botão de salvar ou de saque será usado. |

| **Passos**                                                                                                                                                         |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que os menus FINANCEIRO e COMERCIAL estão visíveis                                                                                                        |
| **QUANDO** clicamos em Caixas, Pagar.me, Despesas Fixas, Relatórios, Prospecção, Planos, Modelos Contrato, Tipos de Pagamento e Bandeiras                          |
| **ENTÃO** abrem as rotas `/caixas`, `/pagarme`, `/despesas-fixas`, `/relatorios`, `/prospeccao`, `/planos`, `/modelos-contrato`, `/tipos-pagamento` e `/bandeiras` |
| **E** cada tela mostra o título do módulo                                                                                                                          |

| **Critérios de aceitação**                                                 |
| :------------------------------------------------------------------------- |
| As telas abrem só para consulta. Nenhum saque, despesa ou plano é gravado. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 05: Abrir os módulos de Gestão, Saúde, Inteligência e Configurações.

| ID       | Descrição                                |
| :------- | :--------------------------------------- |
| C04-CT05 | Os demais menus abrem as próprias telas. |

| **Pré-condições**                                              |
| :------------------------------------------------------------- |
| A conta de teste está autenticada. Nenhum cadastro será salvo. |

| **Passos**                                                                                                                                                                                                                                                      |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que os menus GESTÃO, SAÚDE, INTELIGÊNCIA e CONFIGURAÇÕES estão visíveis                                                                                                                                                                                |
| **QUANDO** percorremos Colaboradores, Funções, Fornecedores, Tipos de Documentos, Atividades, Pontuação, Produtos, Enquetes, Fichas Anamnese, Modelos, Categorias, Perguntas, Inteligência & Automação, Resultados IA, Configurações, Modelo Ficha e Aplicativo |
| **ENTÃO** cada item abre a própria rota                                                                                                                                                                                                                         |
| **E** o título da tela corresponde ao módulo escolhido                                                                                                                                                                                                          |

| **Critérios de aceitação**                                                               |
| :--------------------------------------------------------------------------------------- |
| O menu inteiro que ficou visível para o perfil Administrador abre a tela correspondente. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---
