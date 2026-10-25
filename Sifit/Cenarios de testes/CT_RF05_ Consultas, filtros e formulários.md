## Cenário 05: Consultas, filtros e formulários.

### Caso de Teste 01: Usar os filtros do check-in sem registrar entrada.

| ID       | Descrição                                                            |
| :------- | :------------------------------------------------------------------- |
| C05-CT01 | Os filtros do check-in aparecem e a entrada rápida não é confirmada. |

| **Pré-condições**              |
| :----------------------------- |
| A rota `/checkin` está aberta. |

| **Passos**                                                                                       |
| :----------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela Check-ins                                                           |
| **QUANDO** olhamos a área de filtros                                                             |
| **ENTÃO** aparecem Todos, Presentes agora, Não compareceram, Check-in pendente e o botão Filtros |
| **E** também aparecem Check-in manual, Registrar entrada e Realizar check-in                     |
| **E** não confirmamos nenhum desses três botões de registro                                      |

| **Critérios de aceitação**                                          |
| :------------------------------------------------------------------ |
| Dá para ver os filtros. Nenhuma presença nova é gravada neste caso. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 02: Buscar um cliente que não existe.

| ID       | Descrição                                                   |
| :------- | :---------------------------------------------------------- |
| C05-CT02 | A busca não pode listar um cliente com o texto inexistente. |

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| A rota `/clientes` está aberta e o botão Buscar está visível. |

| **Passos**                                            |
| :---------------------------------------------------- |
| **DADO** que estamos na lista de Clientes             |
| **E** preenchemos `zzzz-nao-existe` no campo de busca |
| **QUANDO** clicamos em Buscar                         |
| **ENTÃO** a lista não mostra um cliente com esse nome |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| A busca inexistente não devolve um cliente com o texto informado. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 03: Abrir Novo Cliente e cancelar.

| ID       | Descrição                                      |
| :------- | :--------------------------------------------- |
| C05-CT03 | Cancelar o cadastro não cria um cliente vazio. |

| **Pré-condições**               |
| :------------------------------ |
| A rota `/clientes` está aberta. |

| **Passos**                                    |
| :-------------------------------------------- |
| **DADO** que estamos na lista de Clientes     |
| **QUANDO** clicamos em Novo Cliente           |
| **E** não preenchemos os campos               |
| **E** clicamos em Cancelar ou Fechar          |
| **ENTÃO** voltamos para a lista               |
| **E** nenhum cliente em branco é acrescentado |

| **Critérios de aceitação**                   |
| :------------------------------------------- |
| O formulário pode ser abandonado sem gravar. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 04: Ver os tipos de relatório sem gerar arquivo.

| ID       | Descrição                                                        |
| :------- | :--------------------------------------------------------------- |
| C05-CT04 | A tela lista os relatórios disponíveis e o arquivo não é gerado. |

| **Pré-condições**                 |
| :-------------------------------- |
| A rota `/relatorios` está aberta. |

| **Passos**                                                                                 |
| :----------------------------------------------------------------------------------------- |
| **DADO** que estamos em Relatórios                                                         |
| **QUANDO** olhamos as opções                                                               |
| **ENTÃO** aparecem Clientes, Colaboradores e Contas a Pagar, além do botão Gerar Relatório |
| **E** não clicamos em Gerar Relatório                                                      |

| **Critérios de aceitação**                                     |
| :------------------------------------------------------------- |
| Os tipos ficam visíveis e nenhum arquivo é baixado neste caso. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 05: Ver os períodos dos Resultados da Inteligência.

| ID       | Descrição                              |
| :------- | :------------------------------------- |
| C05-CT05 | A tela oferece os recortes de período. |

| **Pré-condições**                              |
| :--------------------------------------------- |
| A rota `/inteligencia/resultados` está aberta. |

| **Passos**                                                                 |
| :------------------------------------------------------------------------- |
| **DADO** que estamos em Resultados da Inteligência                         |
| **QUANDO** olhamos os filtros de período                                   |
| **ENTÃO** aparecem Hoje, Últimos 7 dias, Últimos 30 dias e Últimos 90 dias |

| **Critérios de aceitação**                       |
| :----------------------------------------------- |
| Os quatro recortes de período estão disponíveis. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 06: Percorrer as abas de Configurações sem salvar.

| ID       | Descrição                                                         |
| :------- | :---------------------------------------------------------------- |
| C05-CT06 | As abas de configuração abrem e o botão Cancelar desfaz a edição. |

| **Pré-condições**                    |
| :----------------------------------- |
| A rota `/configuracoes` está aberta. |

| **Passos**                                                                                      |
| :---------------------------------------------------------------------------------------------- |
| **DADO** que estamos em Configurações                                                           |
| **QUANDO** clicamos em Home, Biometria, Avaliação, Aniversário, Pagamento, Integrações e Design |
| **ENTÃO** cada aba mostra o próprio conteúdo                                                    |
| **E** se algum campo for alterado, clicamos em Cancelar antes de sair                           |

| **Critérios de aceitação**                             |
| :----------------------------------------------------- |
| Nenhuma configuração da academia é gravada neste caso. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 07: Abrir o Pagar.me sem solicitar saque.

| ID       | Descrição                                                    |
| :------- | :----------------------------------------------------------- |
| C05-CT07 | O painel financeiro abre e a ação de saque não é confirmada. |

| **Pré-condições**              |
| :----------------------------- |
| A rota `/pagarme` está aberta. |

| **Passos**                                                                                                    |
| :------------------------------------------------------------------------------------------------------------ |
| **DADO** que estamos em Pagar.me                                                                              |
| **QUANDO** olhamos o painel                                                                                   |
| **ENTÃO** aparecem Recebimentos, Meios de pagamento, Transações recentes, Repasses, Assinaturas e Chargebacks |
| **E** não clicamos em Solicitar saque nem em Nova cobrança                                                    |

| **Critérios de aceitação**                                        |
| :---------------------------------------------------------------- |
| O painel abre só para leitura. Nenhum saque ou cobrança é criado. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---

### Caso de Teste 08: Abrir o Aplicativo sem moderar postagem.

| ID       | Descrição                                                              |
| :------- | :--------------------------------------------------------------------- |
| C05-CT08 | Notificações, postagens e denúncias aparecem, sem aprovar nem recusar. |

| **Pré-condições**                 |
| :-------------------------------- |
| A rota `/aplicativo` está aberta. |

| **Passos**                                                      |
| :-------------------------------------------------------------- |
| **DADO** que estamos em Aplicativo                              |
| **QUANDO** olhamos a tela                                       |
| **ENTÃO** aparecem Notificações, Postagens e Denúncias          |
| **E** não clicamos em Aprovar, Recusar nem em Criar Notificação |

| **Critérios de aceitação**                           |
| :--------------------------------------------------- |
| A moderação do aplicativo não é alterada neste caso. |

| **Evidência(s)**                              |
| :-------------------------------------------- |
| [Vídeo](https://jam.dev/c/COLE_O_CODIGO_AQUI) |

---
