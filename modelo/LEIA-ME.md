# Como fazer este trabalho

Este texto é para quem vai ajudar e não estava na aula. Ele explica o que entregar, em que ordem, e como cada arquivo deve ficar.

A pasta `OrangeHRM` é o exemplo do professor. Ela serve só para copiar o formato. Não altere nada dentro dela.

A pasta `Sifit` é o meu trabalho. É nela que entram os textos, os casos e os bugs do sistema que eu testei.

A pasta `modelo` é só este guia. Os arquivos em `modelo/exemplo-de-arquivos` mostram o formato vazio. Não coloque resultado real neles.

## O que é o trabalho

O trabalho é um teste manual de um sistema web. A pessoa entra no site, usa as telas, grava o que aconteceu e escreve isso em Markdown.

O documento descreve e evidencia oq foi observado.

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

No meu Sifit a organização ficou assim:

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
    ...
```

O nome do caso tem um espaço depois do código: `CT_RF01_ Login na plataforma.md`. O relatório final também tem um espaço: `4- Relatorio dos testes.md`. Esse espaço está no exemplo do professor. Mantenha.

No OrangeHRM esses quatro relatórios ficam direto na pasta do sistema, sem a pasta `Relatórios`. No meu trabalho a pasta Sifit eles foram agrupados em `Relatórios`. 

## O que cada arquivo responde

**1. Análise de requisitos.** O que o sistema deve fazer. Cada requisito ganha um código RF01, RF02, e assim por diante. Em cada um: uma descrição, o que se espera ver, e o resultado esperado. Escreva só oq a tela ou a aula mostraram. 

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

Grave no Jam. Cada caso executado precisa de um link. Esse link entra como evidência de que o critério de aceitação foi demonstrado. No caso, ele fica assim: `[Vídeo](https://jam.dev/c/...)`.

No bug, a lógica é a mesma: cada bug recebe o link do Jam. O que muda no meu trabalho é o nome do link. Eu uso a ordem do bug, e não a palavra Vídeo: `[BUG:01](https://jam.dev/c/...)`, `[BUG:02](https://jam.dev/c/...)`. (esse foi o meu padrão de organização em nomear os bugs)

O título que eu uso no Jam:

- Caso: `01 - Login com credenciais válidas`
- Bug: `01 - [BUG] Login: Credenciais válidas com espaço a mais`
- Quando o mesmo vídeo mostra mais de uma falha: `[BUGS]`, no plural

Na descrição eu conto o que eu fiz e o que a tela mostrou. Uma ou duas frases bastam. Se aparecer um número, um nome ou uma mensagem importante, eu escrevo exatamente o que estava na tela.

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

Se você for começar agora, use só o Sifit Unialfa: https://sifitalfa.centrion.com.br/. Não precisa repetir o que já foi feito no endereço antigo.

O login dos testes é `marcelo_zandonadi`.

No primeiro endereço, a senha anotada no caso C01-CT01 é `12345678`.

No [sifitalfa](https://sifitalfa.centrion.com.br/), a senha do reteste é `Password`.

## O que não fazer durante o teste

Olhar a tela e abrir um detalhe faz parte do teste.


## Commit

Depois de um conjunto fechado de mudanças, faça um commit. A mensagem diz por que a mudança existe, em uma frase. Exemplo: `Registra a falha do card de avaliações pendentes.`


## Onde olhar quando travar

- Formato das tabelas, dos nomes e o exemplo que o professor trouxe: pasta `OrangeHRM`.
- Meu trabalho em andamento, com os vídeos reais: pasta `Sifit`.
- Arquivos vazios para copiar a estrutura e usar como base: pasta `modelo/exemplo-de-arquivos`.
