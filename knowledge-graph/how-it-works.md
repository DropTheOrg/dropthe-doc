# Como Funciona el Grafo de Conocimiento

El [grafo de conocimiento de DropThe](https://dropthe.org) es un grafo dirigido donde las entidades son nodos y las relaciones son aristas.

## Arquitectura

### Nodos
Cada entidad en la [base de datos DropThe](https://dropthe.org) es un nodo -- [empresas](https://dropthe.org/companies/), [personas](https://dropthe.org/people/), [videojuegos](https://dropthe.org/games/), [peliculas](https://dropthe.org/movies/), [series](https://dropthe.org/series/), [criptomonedas](https://dropthe.org/crypto/), marcas y franquicias.

### Aristas
Las relaciones entre entidades son tipadas y direccionales.

### Inferencia
Algunas relaciones se infieren de conexiones transitivas.

## Pipeline de Datos

1. **Ingestion**: Datos crudos entran de multiples fuentes
2. **Resolucion**: Entidades duplicadas se fusionan
3. **Enlace**: Relaciones se extraen de datos estructurados
4. **Validacion**: Enlaces se puntuan por confianza
5. **Publicacion**: Enlaces verificados aparecen en [paginas de entidades de DropThe](https://dropthe.org)
