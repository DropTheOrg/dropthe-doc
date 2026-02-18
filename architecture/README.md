# Arquitectura del Sitio

[DropThe](https://dropthe.org) esta construido como una red de datos y medios -- un hibrido entre base de datos estructurada, publicacion de medios y plataforma de datos interactiva.

## Estructura de URLs

```
https://dropthe.org/{categoria}/{slug}/
```

| Categoria | Patron | Ejemplo |
|-----------|--------|---------|
| Empresas | `/companies/{slug}/` | [/companies/apple-inc/](https://dropthe.org/companies/apple-inc/) |
| Personas | `/people/{slug}/` | [/people/elon-musk/](https://dropthe.org/people/elon-musk/) |
| Peliculas | `/movies/{slug}/` | [/movies/the-godfather-1972/](https://dropthe.org/movies/the-godfather-1972/) |
| Series | `/series/{slug}/` | [/series/breaking-bad-2008/](https://dropthe.org/series/breaking-bad-2008/) |
| Videojuegos | `/games/{slug}/` | [/games/elden-ring/](https://dropthe.org/games/elden-ring/) |
| Criptomonedas | `/crypto/{slug}/` | [/crypto/bitcoin/](https://dropthe.org/crypto/bitcoin/) |

## Tipos de Pagina

### Paginas de Entidades
El nucleo de DropThe. Cada una de las 2M+ entidades tiene una pagina dedicada generada desde datos estructurados con conexiones del [grafo de conocimiento](../knowledge-graph/), secciones de [inteligencia](../intelligence/) y disponibilidad de streaming.

### Paginas Hub
Landing pages por categoria: [Empresas](https://dropthe.org/companies/), [Personas](https://dropthe.org/people/), [Peliculas](https://dropthe.org/movies/), [Series](https://dropthe.org/series/), [Videojuegos](https://dropthe.org/games/), [Criptomonedas](https://dropthe.org/crypto/)

### Articulos
Periodismo basado en datos publicado a traves del [pipeline de contenido](../pipeline/): [dropthe.org/blog/](https://dropthe.org/blog/)

### Guias
Contenido de referencia curado: [dropthe.org/guides/](https://dropthe.org/guides/)

### Paginas Interactivas
- [Un Dia Como Hoy](https://dropthe.org/on-this-day/) -- 366 paginas diarias
- [Comparador](https://dropthe.org/compare/) -- Comparaciones lado a lado
- [Busqueda](https://dropthe.org/search) -- Busqueda en 2M+ entidades

## Flujo de Datos

```
Fuentes externas → Pipelines de enriquecimiento → PostgreSQL local → Supabase → WordPress → Cloudflare → dropthe.org
```

## Datos Abiertos

- [Datasets en Kaggle](https://www.kaggle.com/dropthe)
- [Datasets en HuggingFace](https://huggingface.co/DropTheHQ)
- [GitHub](https://github.com/DropTheOrg)
