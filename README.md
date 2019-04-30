# Sessões, buscas e navegação na wikimedia

Este repo é a semente para uma análise de padrões de busca e navegação em páginas de projetos da wikimedia (provavelmente wikipedia).

O [exercício original de análise](https://github.com/wikimedia-research/Discovery-Hiring-Analyst-2016) é um problema proposto pela Wikimedia "for candidates applying to be a Data Analyst in the Discovery department at Wikimedia Foundation." O README do projeto original descreve as análises pedidas aos interessados na posição.

## Mais contexto

A [Wikimedia Foundation](https://wikimediafoundation.org/wiki/Home) é uma organização sem fins lucrativos que encoraja o crescimento, desenvolvimento e distribuição de conteúdo de educação grátis e em múltiplas linguagens através de projetos baseados em [wiki](https://en.wikipedia.org/wiki/Wiki). Em 2016 o [Wikimedia Discovery](https://www.mediawiki.org/wiki/Wikimedia_Discovery), um departamento da Wikimidia Foundation, abriu uma seleção de empregos para o cargo de analista de dados. Este repositório é a semente de um exercício para respondermos as perguntas propostas por eles [na proposta de emprego](https://github.com/wikimedia-research/Discovery-Hiring-Analyst-2016):

## Organização

`code`: código para importar + transformar dados para análise, código de funções úteis em mais de um ponto.

`data`: dados criados para essa análise.

`reports`: notebooks das análises.

## Dados pré processados

Como as análises propostas na tarefa original são em sua maioria sobre resultados de buscas e a navegação que acontece depois delas, temos um código inicial para ler os dados originais e criar algumas métricas sobre buscas nas sessões de usuário e sobre a navegaçao depois de cada busca em `code/import-events_to_searches.R`. Executar `Rscript code/import-events_to_searches.R` gera o arquivo `data/search_data.csv`. O script `import-events_to_searches.R` em si é a melhor documentação do que significa cada coluna em `data/search_data.csv`.

Existem 9 variáveis nos dados sendo elas:

* session_id             : Um id único identificando sessões individuais
* search_index           : Um contador de buscas em uma mesma sessão ordenado cronologicamente
* session_start_timestamp: O timestamp que a sessão iniciou
* session_start_date     : A data e hora que a sessão iniciou
* group                  : O grupo que pode ser "a" ou "b"
* results                : A quantidade de resultados que a busca retornou
* num_clicks             : O número de páginas que o usuário visitou a partir da busca
* first_click            : A posição do link da página visitada no mecanismo de busca de páginas
* session_length         : A duração em segundos da sessão


## Dependências

R, com os pacotes `tidyverse`, `lubridate` e `here`.
