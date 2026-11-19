## Cenário 27: Importar avaliações.

### Caso de Teste 01: Acesso, navegação e legibilidade da tela Importar Avaliações.

| ID       | Descrição                                                                                                                               |
| :------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| C27-CT01 | Verificar se o botão "Importar" em Avaliações abre a tela de importação com breadcrumb completo, botão de retorno e boa legibilidade.   |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                        |
| :-------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na tela de Avaliações (`/avaliacoes`)                                                                        |
| **QUANDO** clicarmos no botão "Importar" (abaixo do filtro `Código`)                                                              |
| **ENTÃO** o sistema deverá abrir `/importar-avaliacoes` exibindo o passo a passo (`1 Planilha → 2 Conferência → 3 Resultado`), breadcrumb com `Avaliações`, botão para voltar e contraste legível no modo escuro |

| **Critérios de aceitação**                                                                                                               |
| :--------------------------------------------------------------------------------------------------------------------------------------- |
| A tela de importação deve abrir corretamente, manter o contexto de navegação (`Avaliações`), oferecer retorno e ser legível no modo escuro. |

| **Resultado da execução**                                                                                                                                                                                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A rota `/importar-avaliacoes` abre sem erros na API, porém o breadcrumb exibe `Início > Importar Avaliações` (omitindo `Avaliações`), não existe botão `"Voltar"`, o menu lateral perde o destaque ativo em `Avaliações` e o contraste das letras com o fundo no modo escuro é muito baixo (quase não se enxerga o indicador `1 Planilha`). |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/3662c290-3c8e-470a-84f5-8a0e1c4b1658) |

---

### Caso de Teste 02: Instruções de importação, ausência de planilha modelo e envio de planilha fora do padrão Fineshape.

| ID       | Descrição                                                                                                                                    |
| :------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| C27-CT02 | Verificar se a tela disponibiliza planilha modelo/lista de colunas obrigatórias e como se comporta ao enviar uma planilha fora do padrão.    |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                                                                                                                   |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DADO** que estamos na etapa `1 Planilha` em `/importar-avaliacoes`                                                                                                         |
| **QUANDO** analisarmos as instruções do card `Planilha de avaliações do Fineshape` procurando modelo/colunas obrigatórias e enviarmos uma planilha aleatória fora do padrão  |
| **ENTÃO** o sistema deverá oferecer planilha modelo ou lista de colunas esperadas, rejeitar planilhas sem o cabeçalho do Fineshape e manter boa legibilidade no modo escuro |

| **Critérios de aceitação**                                                                                                              |
| :-------------------------------------------------------------------------------------------------------------------------------------- |
| Deve haver referência clara das colunas obrigatórias, validação do cabeçalho na importação e contraste legível na etapa de conferência. |

| **Resultado da execução**                                                                                                                                                                                                                                  |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falhou.** A tela não disponibiliza planilha modelo nem lista as colunas obrigatórias do Fineshape. Ao enviar uma planilha aleatória fora do padrão, o sistema aceitou o arquivo e avançou para a etapa `2 Conferência`, que também apresenta contraste muito ruim no modo escuro. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/f215de82-2c59-4db8-aa7a-d915cd04a84f) |

---

### Caso de Teste 03: Tentativa de importar arquivo com extensão inválida (`.pdf`).

| ID       | Descrição                                                                                  |
| :------- | :----------------------------------------------------------------------------------------- |
| C27-CT03 | Verificar se o sistema rejeita arquivos com extensão fora dos formatos aceitos (`.pdf`).   |

| **Pré-condições**                                                                                |
| :----------------------------------------------------------------------------------------------- |
| Autenticado no Sifit Unialfa (https://sifitalfa.centrion.com.br/) com a conta marcelo_zandonadi. |

| **Passos**                                                                           |
| :----------------------------------------------------------------------------------- |
| **DADO** que estamos na etapa `1 Planilha` em `/importar-avaliacoes`                 |
| **QUANDO** tentarmos enviar um arquivo `.pdf` na área de importação                  |
| **ENTÃO** o sistema deverá rejeitar o arquivo por não ser `.csv`, `.tsv` ou `.txt`   |

| **Critérios de aceitação**                                                            |
| :------------------------------------------------------------------------------------ |
| O sistema deve bloquear a importação de arquivos com extensões inválidas como `.pdf`. |

| **Resultado da execução**                                                                        |
| :----------------------------------------------------------------------------------------------- |
| **Passou.** O sistema rejeitou o arquivo `.pdf`, comportando-se conforme o critério de aceitação. |

| **Evidência(s)**                                                |
| :-------------------------------------------------------------- |
| [Vídeo](https://jam.dev/c/204365ad-f4af-4cb2-a7a7-def877ee0063) |

