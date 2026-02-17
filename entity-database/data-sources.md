# Data Sources & Enrichment

[DropThe](https://dropthe.org) aggregates data from multiple structured sources through automated enrichment pipelines. No single source provides complete coverage -- the value is in combining and cross-referencing.

## Primary Sources

### Wikidata
The foundation layer. SPARQL queries import entities with structured metadata (identifiers, dates, relationships, categories). Batch API (`wbgetentities`) enriches 50 entities per request for demographics, nationality, gender, and biographical data.

- **Coverage**: 76K people enriched (gender 99%, nationality 66%, birthday 61%)
- **Method**: SPARQL bulk import + batch API enrichment
- **Fields**: QID identifiers, dates, geographic data, occupations, family links

### TMDB (The Movie Database)
Deep enrichment for entertainment entities. Three separate pipelines handle people, movies, and series.

- **Coverage**: 33K people + 144K movies + 12K series = 189K total
- **Fields**: Ratings, runtime, genres, overview, cast/crew, images, popularity
- **Impact**: Movie richness scores jumped from 18.2 to 44.8 average (75% now rated "good")

### Wikipedia
REST API provides human-readable summaries and images for notable entities.

- **Coverage**: 34K entities (29K people, 5K companies, 239 series, 115 movies, 15 games)
- **Fields**: Biographical summaries, profile images, article extracts
- **Pageviews**: 81,932 entities scored for popularity tier assignment

### SEC EDGAR
Financial data for US public companies, sourced from regulatory filings.

- **Coverage**: 6,534 companies enriched (matched from 10,053 SEC entities to our 19,181 companies)
- **Fields**: CIK identifier, revenue, net income, filing data

### World Bank
Macroeconomic and social indicators for countries.

- **Coverage**: 246 countries, 37 indicators, 5,487 data points
- **Fields**: 160 unique fields per country (crime, healthcare, education, economy, environment, governance, demographics, technology)

### CoinGecko
Cryptocurrency market and project data.

- **Coverage**: 12,766 coins
- **Fields**: Descriptions, tags, categories, social links, platforms, contract addresses

### AniList
Anime and manga metadata.

- **Coverage**: 2,552 titles processed
- **Fields**: Demographics (463), format classification (1,634), K-Drama tagging (70)

### IGDB
Video game metadata and images.

- **Coverage**: 6,838+ games
- **Fields**: Images, descriptions, platform data (82% match rate)

## Enrichment Architecture

Enrichment runs as a series of independent Python scripts, each targeting a specific source and entity type. Scripts execute locally against a PostgreSQL database, then push results to production (Supabase).

```
Source API → Python enricher → Local PostgreSQL → Push to Supabase
```

Key design decisions:
- **Local-first**: All enrichment runs against a local database copy to avoid API rate limits on production
- **Batch processing**: Enrichers process thousands of entities per run, not one at a time
- **Idempotent**: Scripts can be re-run safely without creating duplicates
- **Source tracking**: Every enriched field records its source for audit

## Quality Controls

- **Cross-referencing**: Data validated against at least two independent sources where possible
- **Staleness detection**: Records flagged for re-verification based on age
- **Deduplication**: TMDB dedup merged 24,492 duplicate entities (19,339 groups), transferring 25,901 links and 160,988 data fields
- **Garbage removal**: Automated cleanup catches URL strings in date fields, HTML in text fields, NaN values, self-referential links, and orphaned records

See [Data Quality](data-quality.md) for details on quality enforcement.
