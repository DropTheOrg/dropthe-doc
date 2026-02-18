# Calidad de Datos

Mantener la calidad de datos a escala de [2 millones de entidades](https://dropthe.org) requiere pipelines automatizados de deteccion y correccion.

## Barridos de Calidad

### Deduplicacion
- 19,339 grupos duplicados identificados, 24,492 entidades fusionadas
- 25,901 enlaces preservados de duplicados fusionados
- 160,988 campos de datos ganados de registros duplicados

### Canonicalizacion de Slugs
- 155,179 slugs de peliculas + 836 slugs de series reconstruidos a formato consistente `nombre-ano`

### Eliminacion de Datos Basura
| Problema | Registros corregidos |
|----------|---------------------|
| URLs en campos de fecha | 21,839 |
| Enlaces huerfanos | 1,534 |
| Auto-referencias | 285 |
| Descripciones basura | 2,153 |
| Fechas invalidas | 558 |
| HTML en campos de texto | 2,142 |
| Valores NaN/Infinity | 33 |

### Puntuacion de Completitud

Cada entidad recibe una puntuacion de completitud de datos (0-100) que impulsa la prioridad de enriquecimiento.

| Tipo | Puntuacion media |
|------|-----------------|
| Series | 44.6 |
| Peliculas | 44.8 |
| Videojuegos | 44.5 |
| Criptomonedas | 49.2 |
| Empresas | 28.3 |
| Personas | 25.7 |

Mas sobre la [calidad del grafo de conocimiento](../knowledge-graph/how-it-works.md).
