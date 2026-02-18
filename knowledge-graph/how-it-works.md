# Como Funciona o Grafo de Conhecimento

O [grafo de conhecimento do DropThe](https://dropthe.org) e um grafo dirigido onde entidades sao nos e relacoes sao arestas.

## Arquitetura

Cada entidade na [base de dados DropThe](https://dropthe.org) e um no -- [empresas](https://dropthe.org/companies/), [pessoas](https://dropthe.org/people/), [jogos](https://dropthe.org/games/), [filmes](https://dropthe.org/movies/), [series](https://dropthe.org/series/), [criptomoedas](https://dropthe.org/crypto/), marcas e franquias.

## Pipeline de Dados

1. **Ingestao**: Dados brutos entram de multiplas fontes
2. **Resolucao**: Entidades duplicadas sao fundidas
3. **Vinculacao**: Relacoes extraidas de dados estruturados
4. **Validacao**: Links pontuados por confianca
5. **Publicacao**: Links verificados aparecem nas [paginas de entidades do DropThe](https://dropthe.org)
