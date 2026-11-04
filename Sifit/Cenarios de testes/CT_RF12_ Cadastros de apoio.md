## Cenário 12: Validação dos cadastros de apoio (campos obrigatórios).

### Caso de Teste 01: Salvar Planos com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT01 | O cadastro de Planos não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo Plano" em `/planos` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar Plano" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V19) |

---

### Caso de Teste 02: Salvar Fornecedores com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT02 | O cadastro de Fornecedores não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo Fornecedor" em `/fornecedores` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome do fornecedor." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 03: Salvar Turmas com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT03 | O cadastro de Turmas não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Cadastrar Turma" em `/turmas` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome da turma." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 04: Salvar Prospecção com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT04 | O cadastro de Prospecção não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Adicionar Lead" em `/prospeccao` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar Lead" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V20) |

---

### Caso de Teste 05: Salvar Funções com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT05 | O cadastro de Funções não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Função" em `/funcoes` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar Função" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** Nada acontece: nenhuma mensagem aparece e nenhuma requisição é enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V21) |

---

### Caso de Teste 06: Salvar Produtos com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT06 | O cadastro de Produtos não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo" em `/produtos` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/criar-produto/1` retornou 400 e a tela mostrou só "Erro ao salvar produto", sem indicar o campo que falta. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V22) |

---

### Caso de Teste 07: Salvar Bandeiras de Cartão com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT07 | O cadastro de Bandeiras de Cartão não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Bandeira" em `/bandeiras` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome da bandeira." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 08: Salvar Pontuação com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT08 | O cadastro de Pontuação não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Pontuação" em `/pontuacao` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome da pontuação." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 09: Salvar Enquetes com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT09 | O cadastro de Enquetes não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Enquete" em `/enquetes` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/enquete/salvar/1` retornou 200, mas a tela mostrou "Erro ao salvar enquete", sem indicar o que falta. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V23) |

---

### Caso de Teste 10: Salvar Atividades com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT10 | O cadastro de Atividades não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Atividade" em `/atividades` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/salvar-atividade/1` retornou 201 com nome, descrição e pontuação vazios e a lista passou de 4 para 5 atividades, com a linha 5 em branco. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V24) |

---

### Caso de Teste 11: Salvar Tipos de Documentos com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT11 | O cadastro de Tipos de Documentos não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo Tipo" em `/tipos-documento` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome do tipo de documento." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 12: Salvar Exercícios com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT12 | O cadastro de Exercícios não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Adicionar" em `/exercicios` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome do exercicio." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 13: Salvar Categorias Crossfit com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT13 | O cadastro de Categorias Crossfit não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Categoria" em `/categorias-exercicios-crossfit` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório. |

| **Resultado da execução** |
| :------------------------ |
| **Passou.** Apareceu o aviso "Informe o nome da categoria." e nenhuma requisição foi enviada. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V18) |

---

### Caso de Teste 14: Salvar Objetivos de Treino com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT14 | O cadastro de Objetivos de Treino não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo Objetivo" em `/objetivos-treino` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/objetivo-treino/salvar/1` retornou 201 com o nome vazio e a lista passou de 0 para 1 objetivo, com a linha 1 em branco. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V25) |

---

### Caso de Teste 15: Salvar Tipos de Pagamento com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT15 | O cadastro de Tipos de Pagamento não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Novo" em `/tipos-pagamento` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/cria/tipo-pagamento/1` retornou 201 com o nome vazio e a lista passou de 10 para 11 tipos, com a linha 12 em branco. |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V26) |

---

### Caso de Teste 16: Salvar Perguntas de Anamnese com o formulário vazio.

| ID       | Descrição |
| :------- | :-------- |
| C12-CT16 | O cadastro de Perguntas de Anamnese não é salvo com o nome vazio e a tela orienta a pessoa. |

| **Pré-condições** |
| :---------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos** |
| :--------- |
| **DADO** que abrimos "Nova Pergunta" em `/perguntas-anamnese` |
| **E** deixamos todos os campos vazios |
| **QUANDO** clicamos em "Salvar" |
| **ENTÃO** o sistema informa o campo obrigatório e não cria o registro |

| **Critérios de aceitação** |
| :------------------------- |
| O sistema bloqueia o salvamento e informa o campo obrigatório, sem criar registro em branco e sem erro de servidor. |

| **Resultado da execução** |
| :------------------------ |
| **Falhou.** A requisição `POST /api/pergunta-anamnese/salvar/1` retornou 500 e a tela mostrou "Erro ao salvar pergunta". |

| **Evidência(s)** |
| :--------------- |
| [PENDENTE VÍDEO] (roteiro V27) |
