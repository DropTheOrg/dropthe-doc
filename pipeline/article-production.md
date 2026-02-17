# Article Production

Details on how [DropThe](https://dropthe.org) produces data-driven articles.

## Content Types

### Magazine Articles
Long-form data journalism (1,400-2,000 words). Each article centers on a thesis backed by entity database evidence, with 18-22 internal entity links creating a web of cross-references.

Example: [Game Studios with the Best Track Record](https://dropthe.org/gaming/game-studios-best-track-record-data/)

### Data Stories
Shorter analytical pieces highlighting specific patterns found in the knowledge graph or intelligence engine output.

### Guides
Practical content organized around entity categories -- streaming availability, comparison pages, and reference material.

## Entity Linking

Every article weaves links to relevant entity pages on [dropthe.org](https://dropthe.org). The linking system:

1. Identifies entities mentioned in the article text
2. Matches them against the local database using exact and fuzzy search
3. Resolves entity type to construct the correct URL pattern (`/companies/`, `/people/`, `/movies/`, etc.)
4. Links first mention only (no duplicate linking)
5. Handles disambiguation (e.g., "Mad Max" the game vs. "Mad Max" the movie)

Entity links serve dual purposes: they provide reader navigation and they signal to the [knowledge graph](../knowledge-graph/) which entities are contextually related.

## AI Disclosure

All articles that use AI assistance disclose it explicitly. [DropThe](https://dropthe.org) never claims to have tested products, visited locations, or personally experienced services. Language is restricted to: researched, analyzed, compared, reviewed specs.

## Distribution

Published articles are automatically queued for social distribution:
- **X/Twitter**: Reply hack format (Tweet 1: hook without link, Tweet 2: article link)
- **Bluesky**: Direct post with link
- **Additional platforms**: Expanding

The social distribution system runs every 30 minutes, publishing queued content at optimal intervals.
