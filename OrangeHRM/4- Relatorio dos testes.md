# ✅ **Relatório Final de Execução de Testes - OrangeHRM Demo**

**Sistema testado:** OrangeHRM (versão pública demo)
**Responsável:** Aluno aplicado que ama aprender
**Data de execução:** xx/xx/xxxx
**Ambiente:** xxxxx

* Sistema operacional: Windows 11
* Navegador: Chrome 138.0.7204.158
* URL: [https://opensource-demo.orangehrmlive.com](https://opensource-demo.orangehrmlive.com)

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 30                      | 24             | 6              | 6                |

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                   | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s)       |
| --------- | ------------------------ | -------------- | -------------- | -------------- | ------------------------- |
| RF01      | Login                    | 3              | 3              | 2              | BUG-001, BUG-002, BUG-003 |
| RF02      | Dashboard                | 3              | 3              | 0              | -                         |
| RF03      | PIM - Funcionários       | 3              | 2              | 1              | BUG-005                   |
| RF04      | Férias (Leave)           | 3              | 2              | 1              | BUG-004                   |
| RF05      | Recrutamento             | 3              | 2              | 1              | BUG-006                   |
| RF06      | Administração (Admin)    | 3              | 3              | 0              | -                         |
| RF07      | Controle de Ponto (Time) | 3              | 3              | 0              | -                         |
| RF08      | Relatórios               | 3              | N/A            | 0              | -                         |
| RF09      | Diretório                | 3              | 3              | 0              | -                         |
| RF10      | Manutenção               | 3              | 2              | 1              | (Mesmo que BUG-005)       |

---

## 🐞 **Resumo dos Bugs Reportados**

| ID      | Título                                                                         | Severidade | Status |
| ------- | ------------------------------------------------------------------------------ | ---------- | ------ |
| BUG-001 | Ícone de visualizar senha desaparece ao clicar fora do campo                   | Média      | Aberto |
| BUG-002 | Página de login atualiza ao ocorrer erro de autenticação                       | Baixa      | Aberto |
| BUG-003 | Não há mensagem clara de sucesso ou falha no login                             | Média      | Aberto |
| BUG-004 | Não é possível aplicar licença de férias - "No Leave Types with Leave Balance" | Alta       | Aberto |
| BUG-005 | Ícone de “ver senha” desaparece no formulário de criação de funcionário        | Média      | Aberto |
| BUG-006 | Erro de carregamento ao tentar agendar entrevista já agendada                  | Alta       | Aberto |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

* ✅ Passaram: 24
* ❌ Falharam: 6

**Severidade dos bugs:**

* 🟥 Alta: 2
* 🟨 Média: 3
* 🟩 Baixa: 1

---

## 📁 **Evidências e Documentos**

* ✔️ [Plano de Testes (Markdown)]
* ✔️ [Casos de Teste (Planilha ou Markdown)]
* 🐛 [Relatório de Bugs com Evidências em Vídeo]
* 📹 Evidências em vídeo hospedadas no [Jam.dev]

---

## ✅ **Conclusão**

A execução dos testes manuais no OrangeHRM demonstrou **boa estabilidade geral**, mas **apresentou falhas críticas** nos módulos de **Login**, **Recrutamento**, e **Férias**, que impactam diretamente a **experiência do usuário** e **processos-chave** do sistema.

🔍 Identificação da Causa Raiz (Root Cause Analysis)
A identificação da causa raiz é uma etapa essencial no processo de garantia de qualidade (QA), pois busca entender por que um defeito ocorreu, indo além dos sintomas visíveis do problema. Essa análise ajuda a evitar recorrência de falhas, melhorando a qualidade do software a longo prazo.

Ao encontrar um bug, o QA não deve apenas registrá-lo, mas também investigar sua origem. A causa raiz pode estar em erros de lógica no código, falhas de validação, má comunicação entre equipes, requisitos mal definidos ou até inconsistências no ambiente de teste. Ferramentas como 5 Porquês, Diagrama de Ishikawa ou análise de logs podem ser utilizadas para essa investigação.

Identificar corretamente a causa raiz permite que os desenvolvedores corrijam o erro de forma precisa e que o time evite retrabalhos, contribuindo para entregas mais estáveis, eficientes e com menor custo..

