# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari
**Data de execução:** 12/10/2026. Em 24/10/2026, os testes passaram para o endereço indicado abaixo.
**Ambiente:** Sifit Centrion até 23/10/2026. A partir de 24/10/2026, Sifit Unialfa.

* Sistema operacional: Ubuntu 26.04 LTS
* Navegador: Google Chrome 150.0.7871.46
* URL até dia 23/10/2026 : https://sifit.centrion.com.br/
* URL a partir do dia 24/10/2026: https://sifitalfa.centrion.com.br/ 

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 13                      | 1              | 11             | 11               |

Os 7 casos de login foram executados. O C01-CT01 chegou a ter vídeo de entrada no dashboard, mas os bugs BUG-006 e BUG-007 mostram que o login válido falha ou entra com o nome Jair. Por isso ele não entra mais como aprovado. O BUG-005 continua cobrindo C01-CT05 e C01-CT06.

Em 25/10/2026, no Sifit Unialfa, foram gravados C02-CT01, C02-CT02 e C02-CT06. C02-CT03, C02-CT04 e C02-CT05 ainda estão sem vídeo próprio. C02-CT04 e C02-CT05 aparecem dentro dos bugs BUG-009 e BUG-010. Os casos dos cenários 03, 04 e 05 não entram nesta conta.

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                             | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s) |
| --------- | ---------------------------------- | -------------- | -------------- | ---------------- | ------------------- |
| RF01      | Login com credenciais válidas      | 1              | 0              | 2                | BUG-006, BUG-007    |
| RF02      | Validação de credenciais inválidas | 1              | 0              | 1                | BUG-003             |
| RF03      | Campos obrigatórios no login       | 1              | 0              | 1                | BUG-004             |
| RF04      | Espaços extras nas credenciais     | 1              | 0              | 1                | BUG-001             |
| RF05      | Recuperação de senha               | 1              | 0              | 1                | BUG-002             |
| RF06      | Persistência da sessão             | 1              | 0              | 1                | BUG-005             |
| RF07      | Controle de acesso ao dashboard    | 1              | 0              | 1                | BUG-005             |
| RF08      | Página inicial do dashboard        | 5              | 1              | 4                | BUG-008, BUG-009, BUG-010, BUG-011 |

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
| BUG-011 | Card de avaliações pendentes não confere com a lista               | Média      | Aberto |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

* Passaram: 1
* Falharam: 11
* Sem execução: 1, o C02-CT03

**Severidade dos bugs:**

* Alta: 5
* Média: 6
* Baixa: 0

---

## 📁 **Evidências e Documentos**

* Plano de Testes
* Análise de requisitos
* Casos de teste, com vídeo em cada caso
* Relatório de bugs, com o vídeo da falha
* Vídeos no Jam

Os casos C01-CT01 e C01-CT02 têm vídeos próprios. Os casos C01-CT03 a C01-CT07 usam o mesmo vídeo já colocado no bug correspondente. C01-CT05 e C01-CT06 compartilham o vídeo do BUG-005. C02-CT01, C02-CT02 e C02-CT06 têm vídeo próprio. O C02-CT03 ainda está sem vídeo.

---

## ✅ **Conclusão**

O login com credenciais válidas não gerou defeito registrado. As outras verificações falharam. Senha incorreta responde com erro 500, em vez de uma mensagem de autenticação. Campos vazios seguem para a API sem aviso na tela. Espaços nas pontas das credenciais válidas derrubam o login. O link "Esqueci minha senha" não sai da tela. "Manter conectado" pede a senha de novo no retorno, e mesmo assim o `/dashboard` abre sem sessão válida.

Até 23/10/2026 os testes usaram https://sifit.centrion.com.br/. A partir de 24/10/2026, usam https://sifitalfa.centrion.com.br/. A versão interna do sistema não foi anotada.
