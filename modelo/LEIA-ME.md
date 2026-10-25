# Como fazer este trabalho

Este texto é para quem vai ajudar e não estava na aula. Ele explica o que entregar, em que ordem, e como cada arquivo deve ficar.

A pasta `OrangeHRM` é o exemplo do professor. Ela serve só para copiar o formato. Não altere nada dentro dela.

A pasta `Sifit` é o trabalho de verdade. É lá que entram os textos, os casos e os bugs do sistema testado.

A pasta `modelo` é só este guia. Os arquivos em `modelo/exemplo-de-arquivos` mostram o formato vazio. Não coloque resultado real neles.

## O que é o trabalho

O trabalho é um teste manual de um sistema web. A pessoa entra no site, usa as telas, grava o que aconteceu e escreve isso em Markdown.

Não é para programar o sistema. Não é para inventar o que a tela deveria fazer se ninguém viu isso. O texto descreve o que foi observado.

Cada coisa que foi testada e tem vídeo vira um caso de teste. Cada coisa que quebrou vira um bug, também com vídeo. No fim, um relatório conta quantos casos passaram, quantos falharam e quantos bugs foram abertos.

## Ordem do trabalho

Faça nesta ordem. Cada passo usa o anterior.

1. Entrar no sistema e anotar o que a tela faz.
2. Escrever a análise de requisitos, só com o que deu para ver.
3. Escrever o plano de testes: o que entra no teste e o que fica de fora.
4. Escrever os casos de teste, um arquivo por cenário.
5. Executar o caso e gravar um vídeo no Jam.
6. Se o resultado for diferente do que o caso pedia, abrir um bug.
7. Atualizar o relatório final com a conta certa.
8. Fazer um commit em português. Não enviar para o remoto, a menos que peçam.

## Onde fica cada arquivo

No Sifit a organização ficou assim:

```
Sifit/
  Relatórios/
    1-Analise de requisitos.md
    2-plano de testes.md
    3-Relatorio-de-Bugs.md
    4- Relatorio dos testes.md
  Cenarios de testes/
    CT_RF01_ Login na plataforma.md
    CT_RF02_ Página inicial do dashboard.md
```

O nome do caso tem um espaço depois do código: `CT_RF01_ Login na plataforma.md`. O relatório final também tem um espaço: `4- Relatorio dos testes.md`. Esse espaço está no exemplo do professor. Mantenha.

No OrangeHRM esses quatro relatórios ficam direto na pasta do sistema, sem a pasta `Relatórios`. No Sifit eles foram agrupados em `Relatórios`. Siga a pasta do Sifit quando for continuar este trabalho.

## O que cada arquivo responde

**1. Análise de requisitos.** O que o sistema deve fazer. Cada requisito ganha um código RF01, RF02, e assim por diante. Em cada um: uma descrição, o que se espera ver, e o resultado esperado. Escreva só o que a tela ou a aula mostraram. Se o sistema não tem uma lista oficial de requisitos, deixe isso claro no texto. Não crie regra nova para completar a lista.

**2. Plano de testes.** Como o teste vai ser feito. Nome do sistema, ambiente, datas, o que está incluído, o que está fora, ferramentas e riscos. O plano não substitui o caso nem o bug. Ele só diz o recorte.

**3. Casos de teste.** O roteiro de cada verificação. Um arquivo por cenário. Dentro do arquivo, vários casos. Cada caso precisa ter vídeo. Caso sem vídeo não fica no trabalho.

**4. Relatório de bugs.** Uma falha encontrada, com passo a passo, o que deveria acontecer, o que aconteceu, e o vídeo. O número do bug segue a ordem: BUG-001, BUG-002. Não pule número e não reutilize número.

**5. Relatório final.** A conta da execução. Total de casos, quantos passaram, quantos falharam, lista dos bugs e uma conclusão curta. A conta tem de bater com os arquivos. Se um caso saiu, a conta muda. Se um bug entrou, a lista muda.

## Como escrever um caso de teste

O título do arquivo é o cenário. Dentro dele, cada caso tem estas partes, nesta ordem:

- ID, no formato C01-CT01. O primeiro número é o cenário. O segundo é o caso.
- Descrição em uma frase.
- Pré-condições: o que já precisa ser verdade antes de começar.
- Passos em DADO, E, QUANDO e ENTÃO. DADO é a situação. QUANDO é a ação. ENTÃO é o que a tela deve mostrar.
- Critério de aceitação: a frase que decide se passou.
- Evidência: o link do vídeo.

Exemplo de passos:

```
DADO que estamos na página de login
E preenchemos o usuário e a senha
QUANDO clicamos em Entrar
ENTÃO a página inicial abre
```

O ENTÃO descreve o resultado certo. Se a tela fizer outra coisa, o caso falhou e nasce um bug. Não mude o ENTÃO depois para ele “passar”. O bug é que registra a diferença.

As tabelas ficam fechadas. Em Markdown isso é a linha de separação com dois-pontos, para o texto alinhar:

```
| ID       | Descrição        |
| :------- | :--------------- |
| C01-CT01 | Frase do caso.   |
```

Um caso termina com `---`. O próximo caso começa abaixo.

## Vídeo e nome no Jam

Grave no Jam. Cada caso executado recebe um link. No caso, o link se chama `[Vídeo](https://jam.dev/c/...)`.

No bug, o mesmo tipo de link muda de nome para a ordem do bug: `[BUG:01](https://jam.dev/c/...)`, `[BUG:02](https://jam.dev/c/...)`. Não use a palavra Vídeo no bug.

Título do vídeo no Jam, no mesmo padrão dos que já existem:

- Caso: `✅ 01 - Login com credenciais válidas`
- Bug: `✅ 01 - [BUG] Login: Credenciais válidas com espaço a mais`
- Mais de uma falha no mesmo vídeo: `[BUGS]`, no plural

A descrição do vídeo diz o que a pessoa fez e o que a tela mostrou. Uma ou duas frases. Se um número, um nome ou uma mensagem importam, escreva o que apareceu na tela.

O número do caso e o número do bug podem coincidir. O `[BUG]` é o que diferencia os dois.

## Como escrever um bug

Cada bug tem:

- Número e título curto.
- Descrição do que quebrou.
- Severidade, prioridade e status. Status começa em Aberto.
- Passo a passo numerado, para outra pessoa repetir.
- Comportamento esperado e comportamento obtido, lado a lado.
- Ambiente: endereço, sistema operacional, navegador e data.
- Funcionalidade e o caso de teste ligado a essa falha.
- Evidência `[BUG:NN](link)`.

Severidade e prioridade usam Baixa, Média ou Alta. Use Alta quando a pessoa não consegue concluir o fluxo ou quando um valor de dinheiro, de aluno ou de status aparece errado. Use Média quando a tela abre, mas a mensagem, o texto ou o rodapé está errado.

Não escreva como fato o que o vídeo não mostra. Se o Jam não registrou a rede, não diga que a requisição deixou de sair. Diga o que deu para ver na tela.

## O que conta como passou ou falhou

Passou: o vídeo mostra o ENTÃO do caso.

Falhou: o vídeo mostra outra coisa, e existe um bug apontando para esse caso.

Caso sem vídeo não entra na conta. Ele sai do arquivo.

A soma do relatório final precisa fechar: passaram + falharam = total de casos que ficaram. O número de bugs é a quantidade de seções no relatório de bugs.

## Ambiente deste trabalho

Até 23/10/2026 os testes foram em https://sifit.centrion.com.br/.

A partir de 24/10/2026 o professor pediu para continuar em https://sifitalfa.centrion.com.br/. Esse endereço é o Sifit Unialfa.

Quando anotar um vídeo, diga em qual dos dois endereços ele foi gravado. Não troque um pelo outro.

Login usado nos testes: `marcelo_zandonadi`. A senha do primeiro endereço, anotada no caso C01-CT01, é `12345678`. No Unialfa a senha informada para o reteste foi `Password`. Se o login não entrar, registre a mensagem da tela. Não invente outro usuário.

## O que não fazer durante o teste

Olhar a tela e abrir um detalhe faz parte do teste. Confirmar uma ação que muda dado de aluno, de dinheiro ou de mensagem não faz.

Não clique para concluir:

- Cobrar agora, Enviar mensagem, Abrir WhatsApp, Cobrar todos no WhatsApp
- Solicitar saque, Nova cobrança
- Gerar relatório e baixar arquivo
- Aprovar ou recusar post
- Salvar cadastro, salvar configuração, registrar check-in

Pode abrir a janela, ler os valores e fechar. O bug descreve o que já estava na tela.

## Linguagem

Escreva em português, como se estivesse explicando para alguém que vai repetir o teste amanhã.

Uma frase diz uma coisa. Use o nome que está na tela, entre aspas quando for texto literal. Exemplo: a saudação mostrou "Boa tarde, Jair!".

Não use a palavra “deve” para esconder uma hipótese. Se você viu, diga que viu. Se não viu, diga que não deu para confirmar.

## Commit

Depois de um conjunto fechado de mudanças, faça um commit. A mensagem diz por que a mudança existe, em uma frase. Exemplo: `Registra a falha do card de avaliações pendentes.`

Não reescreva o histórico. Não faça push, a menos que peçam.

## Onde olhar quando travar

- Formato das tabelas e dos nomes: pasta `OrangeHRM`.
- Trabalho já feito, com vídeo de verdade: pasta `Sifit`.
- Arquivo vazio para copiar a estrutura: pasta `modelo/exemplo-de-arquivos`.
