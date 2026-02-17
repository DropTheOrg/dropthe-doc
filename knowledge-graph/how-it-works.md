# How the Knowledge Graph Works

The [DropThe knowledge graph](https://dropthe.org) is a directed graph where entities are nodes and relationships are edges.

## Architecture

### Nodes
Every entity in the [DropThe database](https://dropthe.org) is a node -- companies, people, games, movies, series, crypto tokens, brands, and franchises. Each node carries structured metadata specific to its type.

### Edges
Relationships between entities are typed and directional. "Person A works at Company B" is a different edge than "Company B employs Person A," though both may exist.

### Inference
Some relationships are inferred from transitive connections. If Person A founded Company B, and Company B published Game C, the graph can surface the indirect connection between Person A and Game C.

## Data Pipeline

1. **Ingestion**: Raw entity data enters from multiple sources
2. **Resolution**: Duplicate entities are merged using fuzzy matching and unique identifiers
3. **Linking**: Relationships are extracted from structured data and editorial review
4. **Validation**: Links are scored for confidence and flagged if below threshold
5. **Publishing**: Verified links appear on [entity pages across DropThe](https://dropthe.org)
