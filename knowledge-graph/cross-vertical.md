# Cross-Vertical Connections

One of the most powerful features of the [DropThe knowledge graph](https://dropthe.org) is its ability to connect entities across categories that traditional databases keep siloed.

## What Cross-Vertical Means

Most databases organize movies with movies, companies with companies, people with people. The DropThe graph connects them all. A single person entity can link to:

- Companies they founded or work at
- Movies they directed or acted in
- Games they voiced characters in
- Universities they attended
- Countries they were born in
- Crypto projects they invested in
- Franchises they created

This creates a web of intelligence that no single-category database can provide.

## Automated Cross-Linking

The cross-link engine uses 7 automated strategies to discover and create connections:

| Strategy | Links Created | Description |
|----------|--------------|-------------|
| People → Places | 93,000 | Birth countries, nationalities, residence |
| Movies → Places | 80,000 | Production countries, filming locations |
| Movies → Companies | 33,000 | Studios, distributors, production companies |
| Companies → Places | 10,000 | Headquarters, registration countries |
| People → Education | 950 | University attendance, faculty positions |
| Cast/Crew → Titles | 59,859 | Acting, directing, producing credits |
| Crypto → Founders | 78 | Founder/creator relationships |

Total: **216,000+ cross-vertical links** created by automated strategies alone, with millions more from source enrichment.

## Family Network

The knowledge graph maps family relationships across 262,000+ links:

- 74K spouse connections
- 66K parent-child connections
- 66K child-parent connections
- 57K sibling connections
- 69K stub entities created for family members not yet in the database

## Real-World Example

Take [Apple Inc.](https://dropthe.org/companies/apple-inc/) on DropThe. The knowledge graph connects it to:

- **People**: Executives, board members, founders (via works-at, founded-by)
- **Products**: Hardware, software, services (via produces)
- **Universities**: Where its executives studied (via attended → works-at chain)
- **Countries**: Headquarters, operating regions (via headquartered-in)
- **Other companies**: Subsidiaries, acquisitions, competitors (via subsidiary-of, acquired)

No manual curation per page. The graph generates these connections automatically from verified link data.

## Querying Across Verticals

Every [entity page on DropThe](https://dropthe.org) surfaces relevant cross-vertical connections. The "Related Entities" and "Gossip" sections are generated directly from knowledge graph queries, not editorial decisions.

Learn more about [relationship types](relationship-types.md) and [how the graph works](how-it-works.md).
