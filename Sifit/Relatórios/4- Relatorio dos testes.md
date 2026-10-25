# ✅ **Relatório Final de Execução de Testes - Sifit Centrion**

**Sistema testado:** Sifit Centrion
**Responsável:** Maria Eduarda Pacheco Delazari
**Data de execução:** 12/10/2026. A partir de 24/10/2026, os testes continuaram em outro endereço.
**Ambiente:** Sifit Centrion até 23/10/2026. Depois disso, https://sifitalfa.centrion.com.br/

* Sistema operacional: Ubuntu 26.04 LTS
* Navegador: Google Chrome 150.0.7871.46
* URL: https://sifitalfa.centrion.com.br/ a partir de 24/10/2026. A URL usada antes dessa data não foi anotada.

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| ----------------------- | -------------- | -------------- | ---------------- |
| 7                       | 1              | 6              | 5                |

O C01-CT01 foi contado como aprovado porque tem vídeo de execução e não há bug desse fluxo. Os outros seis casos foram contados como falha porque o comportamento obtido está no relatório de bugs. O BUG-005 cobre dois casos, C01-CT05 e C01-CT06.

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo                             | Casos Testados | Casos Passaram | Bugs encontrados | Bug(s) Associado(s) |
| --------- | ---------------------------------- | -------------- | -------------- | ---------------- | ------------------- |
| RF01      | Login com credenciais válidas      | 1              | 1              | 0                | -                   |
| RF02      | Validação de credenciais inválidas | 1              | 0              | 1                | BUG-003             |
| RF03      | Campos obrigatórios no login       | 1              | 0              | 1                | BUG-004             |
| RF04      | Espaços extras nas credenciais     | 1              | 0              | 1                | BUG-001             |
| RF05      | Recuperação de senha               | 1              | 0              | 1                | BUG-002             |
| RF06      | Persistência da sessão             | 1              | 0              | 1                | BUG-005             |
| RF07      | Controle de acesso ao dashboard    | 1              | 0              | 1                | BUG-005             |

---

## 🐞 **Resumo dos Bugs Reportados**

| ID      | Título                                                             | Severidade | Status |
| ------- | ------------------------------------------------------------------ | ---------- | ------ |
| BUG-001 | Falha no login ao inserir espaços extras nas credenciais válidas   | Média      | Aberto |
| BUG-002 | Link "Esqueci minha senha" não funciona                            | Média      | Aberto |
| BUG-003 | Erro interno do servidor ao validar credenciais inválidas no login | Alta       | Aberto |
| BUG-004 | Ausência de validação de campos obrigatórios no login              | Média      | Aberto |
| BUG-005 | Falha na persistência e no controle da sessão de login             | Alta       | Aberto |

---

## 📈 **Gráfico de Resultado (Texto Alternativo)**

**Casos por status:**

* Passaram: 1
* Falharam: 6

**Severidade dos bugs:**

* Alta: 2
* Média: 3
* Baixa: 0

---

## 📁 **Evidências e Documentos**

* Plano de Testes
* Análise de requisitos
* Casos de teste, com vídeo em cada caso
* Relatório de bugs, com o vídeo da falha
* Vídeos no Jam

Os casos C01-CT01 e C01-CT02 têm vídeos próprios. Os casos C01-CT03 a C01-CT07 usam o mesmo vídeo já colocado no bug correspondente. C01-CT05 e C01-CT06 compartilham o vídeo do BUG-005.

---

## ✅ **Conclusão**

O login com credenciais válidas não gerou defeito registrado. As outras verificações falharam. Senha incorreta responde com erro 500, em vez de uma mensagem de autenticação. Campos vazios seguem para a API sem aviso na tela. Espaços nas pontas das credenciais válidas derrubam o login. O link "Esqueci minha senha" não sai da tela. "Manter conectado" pede a senha de novo no retorno, e mesmo assim o `/dashboard` abre sem sessão válida.

A versão do sistema não foi anotada. A URL usada até 23/10/2026 também não. Em 24/10/2026, o professor pediu para continuar os testes em https://sifitalfa.centrion.com.br/.
