# Mortes por tuberculose

## Conextualização do problema de pesquisa

Eu (Michel) assistia a um noticiário que mencionava o combate à tuberculose (TB) como parte dos Objetivos de Desenvolvimento do Milênio das Nações Unidas. Desejando saber a gravidade da TB, naveguei no site da Organização Mundial da Saúde (OMS) e encontrei um conjunto de dados com o número de casos e óbitos de TB por país por ano, de 2007 a 2013. Isso, por sua vez, levantou a questão de saber se um número alto (ou baixo) pode ser principalmente devido ao país ter uma grande (ou pequena) população. Um pouco mais de navegação revelou que a OMS também possui dados populacionais de 1990 a 2013.

Foram dados suficientes para a pergunta confusa: quão séria é a tuberculose? Era hora de torná-lo preciso. Optei por medir o efeito da TB em termos de óbitos, o que levou às seguintes questões:

- Qual é o número total, mínimo, máximo e médio de mortes por TB?
- Qual é a taxa de mortalidade (número de mortes dividido pela população) de cada país?
- Quais países têm o menor e o maior número de mortes?
- Quais países têm a menor e a maior taxa de mortalidade?

Responder a essas perguntas para o mundo inteiro e por sete anos (2007-2013) seria um pouco demais para este projeto inicial. Era necessário um subconjunto. Resolvi pegar apenas os dados mais recentes de 2013 e, sendo português, focar nos países de língua portuguesa. Um deles, o Brasil, faz parte do grupo BRICS das principais economias emergentes, portanto, para maior diversidade, os outros quatro países também seriam incluídos: Rússia, Índia, China e África do Sul. O projeto foi finalmente definido! Eu adicionei links para os dados abaixo se você quiser dar uma olhada!

## Fonte de dados:

- [POPULAÇÃO DA OMS - DADOS POR PAÍS (ÚLTIMO ANO)](https://github.com/mwermelinger/Learn-to-code-for-data-analysis/raw/master/1_Having_a_go_at_it/WHO%20POP%20TB%20all.xls)

- [MORTALIDADE E PREVALÊNCIA DA OMS - DADOS POR PAÍS (2007 - PRESENTE)](https://github.com/mwermelinger/Learn-to-code-for-data-analysis/raw/master/1_Having_a_go_at_it/WHO%20POP%20TB%20some.xls)

## Dataframes com Pandas


![Pandas](https://www.open.edu/openlearn/pluginfile.php/1348056/mod_oucontent/oucontent/69043/cbfeded3/7376536f/ou_futurelearn_learn_to_code_fig_1034.jpg)


Três linhas de código foram necessárias para cada país, para armazenar o número de mortes, armazenar a população e calcular a taxa de mortalidade. Com cerca de 200 países no mundo, minha análise trivial exigiria 400 variáveis ​​e digitação de quase 600 linhas de código! A vida é muito curta para ser gasta assim.

Em vez de usar uma variável separada para cada dado, é melhor organizar os dados como uma tabela de linhas e colunas.

|País       |Mortes     |População  |
|-----------|-----------|-----------|
|Angola     | 6900      | 21472     |
|Brasil     | 4400      | 200362    |
|Portugal   | 140       | 10608     |

Dessa forma, ao invés de 400 variáveis, preciso apenas de uma que armazene a tabela inteira. Em vez de escrever uma expressão de uma milha que adiciona 200 variáveis ​​para obter o total de mortes, escreverei uma expressão curta que calcula o total da coluna 'Mortes', não importa quantos países (linhas) existam.

Para organizar os dados em tabelas e fazer cálculos nessas tabelas, você e eu usaremos o módulo pandas, que está incluído no Anaconda e no CoCalc. Um módulo é um pacote de vários pedaços de código que podem ser usados ​​individualmente. O módulo pandas fornece recursos de análise de dados muito extensos e avançados para complementar o Python. Este curso apenas arranha a superfície dos pandas.

Eu tenho que dizer ao computador que vou usar um módulo.


## Obtenção dos dados

Criei uma tabela com todos os dados necessários para o projeto e salvei em um arquivo Excel. O Excel é um aplicativo popular para criar, editar e analisar dados tabulares. Você não precisará do Excel para concluir este curso, mas muitos conjuntos de dados são fornecidos como arquivos do Excel.

Abra o arquivo de dados WHO POP TB some.xls . O arquivo é codificado usando UTF-8, uma codificação de caracteres que permite letras acentuadas. Não abra ou edite o arquivo, pois você pode alterar a forma como ele é codificado, o que levará a erros mais tarde. Se você quiser ver seu conteúdo, faça uma cópia do arquivo e veja a cópia.

Coloque o arquivo de dados na mesma pasta (ou projeto CoCalc) onde você salvou seu caderno de exercícios. Feito? Ótimo, vamos continuar carregando os dados – você aprenderá como fazer isso na próxima seção.