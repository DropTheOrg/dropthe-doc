# Fuentes de Datos y Enriquecimiento

[DropThe](https://dropthe.org) agrega datos de multiples fuentes estructuradas a traves de pipelines de enriquecimiento automatizados.

## Fuentes Principales

| Fuente | Cobertura | Campos |
|--------|-----------|--------|
| Wikidata | 76K personas | Genero, nacionalidad, fechas, relaciones |
| TMDB | 189K entidades (33K personas, 144K peliculas, 12K series) | Valoraciones, duracion, generos, reparto, imagenes |
| Wikipedia | 34K entidades | Biografias, imagenes, extractos |
| SEC EDGAR | 6,534 empresas | Ingresos, beneficio neto, datos regulatorios |
| Banco Mundial | 246 paises, 37 indicadores | Economia, salud, educacion, medio ambiente |
| CoinGecko | 12,766 criptomonedas | Descripciones, categorias, enlaces sociales |
| AniList | 2,552 titulos | Demograficos, formatos, clasificacion |
| IGDB | 6,838+ videojuegos | Imagenes, descripciones, plataformas |

## Arquitectura

El enriquecimiento se ejecuta como scripts Python independientes contra una base de datos PostgreSQL local, luego se envian los resultados a produccion (Supabase).

Controles de calidad: deduplicacion, deteccion de datos basura, validacion cruzada entre fuentes.

Ver [Calidad de datos](data-quality.md) para mas detalles.
