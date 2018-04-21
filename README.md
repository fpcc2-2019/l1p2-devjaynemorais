# Seções, buscas e navegação na wikimedia

Este repo é a semente para uma análise de padrões de busca e navegação em páginas de projetos da wikimedia (provavelmente wikipedia).

O [exercício original de análise](https://github.com/wikimedia-research/Discovery-Hiring-Analyst-2016) é um problema proposto pela Wikimedia "for candidates applying to be a Data Analyst in the Discovery department at Wikimedia Foundation." O README do projeto original descreve as análises pedidas aos interessados na posição.

## Organização

`code`: código para importar + transformar dados para análise, código de funções úteis em mais de um ponto.

`data`: dados criados para essa análise.

`reports`: notebooks das análises.

## O que já temos

Como as análises propostas na tarefa original são em sua maioria sobre resultados de buscas e a navegação que acontece depois delas, já há código para ler os dados originais e criar algumas métricas sobre buscas nas sessões de usuário e sobre a navegaçao depois de cada busca em `code/import-events_to_searches.R`. Executar `Rscript code/import-events_to_searches.R` gera o arquivo `data/search_data.csv`. O script `import-events_to_searches.R` em si é a melhor documentação do que significa cada coluna em `data/search_data.csv`.

## Dependências

R, com os pacotes `tidyverse`, `lubridate` e `here`.
