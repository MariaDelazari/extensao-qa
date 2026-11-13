# Roteiro dos vídeos a gravar

Entrar em https://sifitalfa.centrion.com.br/ com o login `marcelo_zandonadi` e a senha `password`, no Google Chrome.

Depois de gravar no Jam, cole o link no GitHub: no caso, troque `coloque o link do video aqui` pelo link, deixando `[Vídeo](link)`; no bug, faça o mesmo, deixando `[BUG:NN](link)`. Um mesmo vídeo serve para o caso e para o bug. Se o resultado for diferente do que está escrito, corrija o resultado e avise no grupo.

| Vídeo | Quem | O que fazer | O que mostrar | Caso | Bug |
| :---- | :--- | :---------- | :------------ | :--- | :-- |
| V04 | Maria | Página Inicial → "Ver detalhes" do card de avaliações pendentes | Card com 0 e lista com 4 pendentes | C02-CT08 | BUG-015 |
| V07 | Maria | Clientes → digitar "abc" no campo Código | O campo aceita letras | C04-CT16 | BUG-017 |
| V10 | Maria | Matrículas (3 ativas) → Clientes com Status "Ativo" (1) → "Todos" e buscar Marcelo e Rafaela | Matrículas ativas de clientes inativos | C06-CT14 | BUG-018 |
| V12 | Daniel | Contas a Pagar → Nova Conta → salvar vazio | Só "Erro ao salvar conta a pagar", sem dizer o que falta | C13-CT05 | BUG-020 |
| V13 | Rafael | Caixas → Abrir Caixa → confirmar vazio | "Erro no servidor. Erro interno inesperado." | C12-CT06 | BUG-021 |
| V14 | Keltton | Check-in → mostrar os indicadores e a tabela → Presenças | "3 Check-ins hoje" com a lista vazia | C09-CT09 | BUG-022 |
| V15 | Keltton | Página Inicial (pico) → Check-in (horário de maior movimento) | "00h - 01h" contra "18h às 20h" | C09-CT12 | BUG-023 |
| V16 | Daniel | Avaliações → Cadastrar Avaliação → salvar sem aluno | Aviso "Selecione um aluno." | C10-CT04 | - |
| V17 | Ville | Colaboradores → Novo Colaborador → salvar vazio | "Erro no servidor. Erro interno inesperado." | C16-CT04 | BUG-024 |
| V18 | Maria | Salvar vazio, uma tela depois da outra: Bandeiras, Pontuação, Tipos de Documentos e Categorias Crossfit | Cada tela avisa que o nome é obrigatório | C19-CT01, C19-CT02, C19-CT05 e C19-CT06 | - |
| V19 | Maria | Planos → Novo Plano → Salvar vazio | Se aparecer "Preencha este campo.", o caso passou e o bug é cancelado | C05-CT12 | BUG-025 (em revisão) |
| V20 | Rafael | Prospecção → Adicionar Lead → Salvar vazio | Igual ao V19 | C15-CT07 | BUG-026 (em revisão) |
| V21 | Ville | Funções → Nova Função → Salvar vazio | Igual ao V19 | C16-CT13 | BUG-027 (em revisão) |
| V22 | Keltton | Produtos → Novo → Salvar vazio | Só "Erro ao salvar produto", sem dizer o campo | C17-CT04 | BUG-028 |
| V23 | Maria | Enquetes → Nova Enquete → Salvar vazio | "Erro ao salvar enquete", sem dizer o que falta | C19-CT03 | BUG-029 |
| V24 | Maria | Atividades → Nova Atividade → Salvar vazio | Linha nova sem nome | C19-CT04 | BUG-030 |
| V25 | Maria | Objetivos de Treino → Novo → Salvar vazio | Linha nova sem nome | C19-CT07 | BUG-031 |
| V26 | Maria | Tipos de Pagamento → Novo → Salvar vazio | Linha nova sem nome | C19-CT08 | BUG-032 |
| V27 | Maria | Perguntas de Anamnese → Nova Pergunta → Salvar vazio | Só "Erro ao salvar pergunta", sem dizer o que falta | C19-CT09 | BUG-033 |

Antes do V24, V25 e V26, excluir os registros em branco que sobraram dos testes anteriores (Atividades 5, Objetivos de Treino 1 e Tipos de Pagamento 12). Depois de gravar, excluir também os novos.

Os outros casos sem vídeo não estão neste roteiro, inclusive o C11-CT05 (Turmas), que fica com o Ville. Cada um grava os casos do seu cenário seguindo os passos do próprio caso, na pasta `Cenarios de testes/Pendentes de evidencias`.
