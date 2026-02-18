# Entity Types

The [DropThe entity database](https://dropthe.org) organizes 1.94 million entities across 17 primary categories.

## Core Categories

### Companies
400,000+ technology firms, studios, publishers, and corporations. Enriched with SEC EDGAR financial data (revenue, net income, CIK identifiers) for 6,500+ public companies. Includes subsidiaries, parent companies, and cross-linked executives.

Browse: [dropthe.org/companies/](https://dropthe.org/companies/)

### People
500,000+ executives, creators, actors, directors, and public figures. Enriched with biographical data from Wikidata (gender 99%, nationality 66%, birthday 61%), TMDB (33K+ with filmography), and Wikipedia (29K+ with bios and images). 100K+ people have ethical [Good Scores](../intelligence/good-score.md).

Browse: [dropthe.org/people/](https://dropthe.org/people/)

### Movies
300,000+ films with cast, crew, studio connections, and streaming availability. TMDB deep enrichment covers 144K movies with ratings, runtime, genres, and overview data. Average data richness score: 44.8 out of 100.

Browse: [dropthe.org/movies/](https://dropthe.org/movies/)

### Series
150,000+ TV shows and streaming series. 12K enriched via TMDB with episode data, network information, and cast/crew connections. Streaming availability tracked across major platforms.

Browse: [dropthe.org/series/](https://dropthe.org/series/)

### Games
200,000+ video games across all platforms. Connected to studios, publishers, and franchises. IGDB enrichment in progress (6,800+ with images, 82% match rate).

Browse: [dropthe.org/games/](https://dropthe.org/games/)

### Crypto
80,000+ cryptocurrency tokens and blockchain projects. CoinGecko enrichment covers 12,700+ coins with descriptions, tags, categories, social links, platforms, and contract addresses. 39 major crypto entities linked to their founders.

Browse: [dropthe.org/crypto/](https://dropthe.org/crypto/)

### Countries
246 countries with World Bank indicator data spanning 37 economic, social, and environmental metrics. 160 unique data fields per country covering crime, healthcare, education, economy, environment, governance, demographics, and technology.

Browse: [dropthe.org/countries/](https://dropthe.org/countries/)

### Universities
21,677 universities from 203 countries, imported via Wikidata SPARQL. Connected to 64,467 alumni and faculty via entity links. Geo-linked to countries (19,868 links) and cities (2,653 links).

Browse: [dropthe.org/universities/](https://dropthe.org/universities/)

## Extended Categories

| Category | Count | Description |
|----------|-------|-------------|
| Brands | 100,000+ | Consumer brands, product lines, trademark holders |
| Franchises | 73+ | Cross-media franchises (games, movies, series, merchandise) |
| Apps | 7,000+ | Mobile and desktop applications |
| Books | 5,700+ | Published books and literature |
| Manga | 2,000+ | Japanese manga and comics (AniList enriched) |
| Events | 1,800+ | Industry events, conferences, ceremonies |
| Products | 1,600+ | Consumer products and hardware |
| Awards | 74 | Major awards (Nobel, Oscar, Grammy, etc.) with 1,292 winner/nominee links |
| Supplements | 385 | Health and dietary supplements |
| Streaming Services | 37 | Platform entities (Netflix, Disney+, etc.) |

## Popularity Tiers

Entities are classified into visibility tiers based on Wikipedia pageview data (81,932 entities scored):

| Tier | Description | Indexed |
|------|-------------|---------|
| S | Global recognition (top 0.1%) | Yes |
| A | High visibility | Yes |
| B | Moderate visibility | Yes |
| C | Niche recognition | No (noindex) |
| D | Low visibility | No (noindex) |

Only S, A, and B tier entities are included in sitemaps for search engine crawling. All entity pages remain publicly accessible regardless of tier.
