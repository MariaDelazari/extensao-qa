# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari
**Data de execução:** 12/10/2026. Em 24/10/2026, os testes passaram para o endereço indicado abaixo. Os cenários C03 a C12 foram executados em 28/10/2026.
**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, Sifit Unialfa.

* Sistema operacional: Ubuntu 26.04 LTS
* Navegador: Google Chrome 150.0.7871.46
* URL até dia 23/10/2026 : https://sifit.centrion.com.br/
* URL a partir do dia 24/10/2026: https://sifitalfa.centrion.com.br/ 

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 44                      | 13             | 31             | 33               |

Os 10 casos de C01 e C02 falharam: o C02-CT02 deixou de constar como aprovado, porque os BUG-008, 009 e 010 apontam para ele, e o C02-CT03 falhou com o BUG-015. Os 34 casos novos (C03 a C12) foram executados em 28/10/2026: 13 passaram e 21 falharam. Passaram: C04-CT02, C04-CT03, C04-CT05, C05-CT01, C05-CT02, C10-CT01 e C12-CT02, CT03, CT07, CT08, CT11, CT12 e CT13. 13 + 31 = 44.

Os casos novos foram executados por automação de navegador (Google Chrome) e aguardam os vídeos ([PENDENTE VÍDEO]) e as evidências dos bugs ([PENDENTE BUGS]). O roteiro está em `5-Roteiro-de-videos.md`.

----------------------- | -------------- | -------------- | ---------------- |
| 10                      | 1              | 9              | 11               |

Os 7 casos de login foram executados. O C01-CT01 chegou a ter vídeo de entrada no dashboard, mas os bugs BUG-006 e BUG-007 mostram que o login válido falha ou entra com o nome Jair. Por isso ele não entra mais como aprovado. O BUG-005 continua cobrindo C01-CT05 e C01-CT06.

Na página inicial ficaram só os casos com vídeo: C02-CT01, C02-CT02 e C02-CT03. O C02-CT02 passou. C02-CT01 e C02-CT03 falharam. Os bugs BUG-008, BUG-009 e BUG-010 continuam no relatório porque cada um tem o próprio vídeo.

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                              | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s) |
| --------- | ---------------------------------- | -------------- | -------------- | ---------------- | ------------------- |
| RF01      | Login com credenciais válidas      | 1              | 0              | 3                | BUG-006, BUG-007, BUG-011 |
| RF02      | Validação de credenciais inválidas | 1              | 0              | 1                | BUG-003             |
| RF03      | Campos obrigatórios no login       | 1              | 0              | 1                | BUG-004             |
| RF04      | Espaços extras nas credenciais     | 1              | 0              | 1                | BUG-001             |
| RF05      | Recuperação de senha               | 1              | 0              | 1                | BUG-002             |
| RF06      | Persistência da sessão             | 1              | 0              | 1                | BUG-005             |
| RF07      | Controle de acesso ao dashboard    | 1              | 0              | 1                | BUG-005             |
| RF08      | Página inicial do dashboard        | 3              | 0              | 4                | BUG-008, BUG-009, BUG-010, BUG-015 (o BUG-007 também afeta o C02-CT01) |
| RF09      | Dashboard                          | 3              | 0              | 3                | BUG-012, BUG-013, BUG-014 |
| RF10      | Gestão de clientes                 | 5              | 3              | 2                | BUG-016, BUG-017    |
| RF11      | Gestão de matrículas               | 3              | 2              | 1                | BUG-018             |
| RF12      | Contas a receber                   | 1              | 0              | 1                | BUG-019             |
| RF13      | Contas a pagar                     | 1              | 0              | 1                | BUG-020             |
| RF14      | Caixas                             | 1              | 0              | 1                | BUG-021             |
| RF15      | Check-in e presenças               | 2              | 0              | 2                | BUG-022, BUG-023    |
| RF16      | Avaliações físicas                 | 1              | 1              | 0                | -                   |
| RF17      | Colaboradores                      | 1              | 0              | 1                | BUG-024             |
| RF18      | Cadastros de apoio                 | 16             | 7              | 9                | BUG-025 a BUG-033   |

--------- | ---------------------------------- | -------------- | -------------- | ---------------- | ------------------- |
| RF01      | Login com credenciais válidas      | 1              | 0              | 3                | BUG-006, BUG-007, BUG-011 |
| RF02      | Validação de credenciais inválidas | 1              | 0              | 1                | BUG-003             |
| RF03      | Campos obrigatórios no login       | 1              | 0              | 1                | BUG-004             |
| RF04      | Espaços extras nas credenciais     | 1              | 0              | 1                | BUG-001             |
| RF05      | Recuperação de senha               | 1              | 0              | 1                | BUG-002             |
| RF06      | Persistência da sessão             | 1              | 0              | 1                | BUG-005             |
| RF07      | Controle de acesso ao dashboard    | 1              | 0              | 1                | BUG-005             |
| RF08      | Página inicial do dashboard        | 3              | 1              | 3                | BUG-008, BUG-009, BUG-010 |

---

## 🐞 **Resumo dos Bugs Reportados**

| ID      | Título                                                             | Severidade | Status |
| ------- | ------------------------------------------------------------------ | ---------- | ------ |
| BUG-001 | Falha no login ao inserir espaços extras nas credenciais válidas   | Média      | Aberto |
| BUG-002 | Link "Esqueci minha senha" não funciona                            | Média      | Aberto |
| BUG-003 | Erro interno do servidor ao validar credenciais inválidas no login | Alta       | Aberto |
| BUG-004 | Ausência de validação de campos obrigatórios no login              | Média      | Aberto |
| BUG-005 | Falha na persistência e no controle da sessão de login             | Alta       | Aberto |
| BUG-006 | Erro interno do servidor ao autenticar com credenciais válidas     | Alta       | Aberto |
| BUG-007 | Inconsistência na identificação do usuário e na autenticação       | Média      | Aberto |
| BUG-008 | Radar de Evasão mostra a faixa errada de alunos                    | Média      | Aberto |
| BUG-009 | Cobrança e perfil de Rafael Santos não fecham com a lista          | Alta       | Aberto |
| BUG-010 | Card de valor em aberto não confere com o detalhe                  | Alta       | Aberto |
| BUG-011 | O campo de senha não deixa ver o que foi digitado                  | Média      | Aberto |
| BUG-012 | Dashboard mostra o título "Despesas Fixas"                         | Média      | Aberto |
| BUG-013 | Títulos dos gráficos do Dashboard ficam ilegíveis                  | Baixa      | Aberto |
| BUG-014 | Quantidade de alunos em risco diverge entre as telas               | Alta       | Aberto |
| BUG-015 | Card de avaliações pendentes mostra 0, mas a lista tem pendentes   | Alta       | Aberto |
| BUG-016 | Paginação de clientes mostra 3 páginas para 1 resultado            | Baixa      | Aberto |
| BUG-017 | Campo Código da busca de clientes aceita letras                    | Baixa      | Aberto |
| BUG-018 | Matrículas ativas pertencem a clientes inativos                    | Alta       | Aberto |
| BUG-019 | Totais de Contas a Receber não fecham com a listagem               | Média      | Aberto |
| BUG-020 | Erro 500 ao salvar conta a pagar com campos vazios                 | Média      | Aberto |
| BUG-021 | Erro 500 ao abrir caixa com campos vazios                          | Média      | Aberto |
| BUG-022 | Check-ins do dia não batem com a lista de check-ins                | Alta       | Aberto |
| BUG-023 | Horário de pico diferente entre Página Inicial e Check-in          | Baixa      | Aberto |
| BUG-024 | Erro 500 ao salvar colaborador com campos vazios                   | Média      | Aberto |
| BUG-025 | Cadastro de Planos não avisa nada ao salvar vazio                  | Média      | Aberto |
| BUG-026 | Cadastro de Prospecção não avisa nada ao salvar vazio              | Média      | Aberto |
| BUG-027 | Cadastro de Funções não avisa nada ao salvar vazio                 | Média      | Aberto |
| BUG-028 | Erro genérico ao salvar produto vazio                              | Baixa      | Aberto |
| BUG-029 | Erro genérico ao salvar enquete vazia                              | Baixa      | Aberto |
| BUG-030 | Atividades permite salvar registro em branco                       | Média      | Aberto |
| BUG-031 | Objetivos de Treino permite salvar registro em branco              | Média      | Aberto |
| BUG-032 | Tipos de Pagamento permite salvar registro em branco               | Média      | Aberto |
| BUG-033 | Erro 500 ao salvar pergunta de anamnese vazia                      | Média      | Aberto |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

* Passaram: 13
* Falharam: 31

**Severidade dos bugs:**

* Alta: 9
* Média: 18
* Baixa: 6

---

## 📁 **Evidências e Documentos**

* Plano de Testes
* Análise de requisitos
* Casos de teste (C01 a C12); os casos C03 a C12 aguardam o vídeo
* Relatório de bugs, com o vídeo da falha
* Vídeos no Jam
* Roteiro dos vídeos a gravar (`5-Roteiro-de-videos.md`)

Os casos C01-CT01 e C01-CT02 têm vídeos próprios. Os casos C01-CT03 a C01-CT07 usam o mesmo vídeo já colocado no bug correspondente. C01-CT05 e C01-CT06 compartilham o vídeo do BUG-005. C02-CT01, C02-CT02 e C02-CT03 têm vídeo próprio.

---

## ✅ **Conclusão**

Dos 44 casos, 13 passaram e 31 falharam, com 33 bugs abertos. Os 10 casos de login e página inicial falharam: o login válido falha com erro 500 ou entra mostrando o nome Jair, senha incorreta responde com erro 500, campos vazios seguem para a API sem aviso, espaços nas pontas derrubam o login, o link "Esqueci minha senha" não sai da tela e a sessão não é controlada. Nos módulos testados em 28/10/2026, os problemas mais frequentes são formulários vazios que geram erro 500 (Contas a Pagar, Caixas, Colaboradores, Perguntas de Anamnese), formulários que aceitam registro em branco (Atividades, Objetivos de Treino e Tipos de Pagamento) ou não avisam nada (Planos, Prospecção e Funções), e números que mudam de uma tela para outra (alunos em risco, avaliações pendentes, check-ins do dia, matrículas ativas contra clientes ativos e totais de contas a receber). A validação de campo obrigatório funciona em Clientes, Matrículas, Avaliações, Fornecedores, Turmas, Bandeiras, Pontuação, Tipos de Documentos, Exercícios e Categorias Crossfit.

Ficaram sem caso de teste, por não terem sido exercitados: cadastro completo com dados válidos, edição e exclusão nas telas novas, Pagar.me, Inteligência & Automação, Resultados IA, Relatórios, Configurações, Aplicativo, Fichas de Treino e Anamnese. O teste de formulário vazio criou 3 registros em branco no ambiente (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12), que devem ser excluídos.

Até 23/10/2026 os testes usaram https://sifit.centrion.com.br/. A partir de 24/10/2026, usam https://sifitalfa.centrion.com.br/, e os cenários C03 a C12 foram executados em 28/10/2026. A versão interna do sistema não foi anotada.
