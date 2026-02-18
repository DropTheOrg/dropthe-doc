# Site Architecture

[DropThe](https://dropthe.org) is built as a data utility media network -- a hybrid between a structured database, a media publication, and an interactive data platform. Here's how it all fits together.

## URL Structure

Every entity follows a consistent URL pattern based on its category:

```
https://dropthe.org/{category}/{slug}/
```

| Category | URL Pattern | Example |
|----------|------------|---------|
| Companies | `/companies/{slug}/` | [/companies/apple-inc/](https://dropthe.org/companies/apple-inc/) |
| People | `/people/{slug}/` | [/people/elon-musk/](https://dropthe.org/people/elon-musk/) |
| Movies | `/movies/{slug}/` | [/movies/the-godfather-1972/](https://dropthe.org/movies/the-godfather-1972/) |
| Series | `/series/{slug}/` | [/series/breaking-bad-2008/](https://dropthe.org/series/breaking-bad-2008/) |
| Games | `/games/{slug}/` | [/games/elden-ring/](https://dropthe.org/games/elden-ring/) |
| Crypto | `/crypto/{slug}/` | [/crypto/bitcoin/](https://dropthe.org/crypto/bitcoin/) |

Movies and series use `name-year` slug format for disambiguation (multiple titles can share a name).

## Page Types

### Entity Pages
The core of DropThe. Each of the 2M+ entities has a dedicated page generated from structured data. Entity pages include:

- Structured metadata (type-specific fields)
- [Knowledge graph](../knowledge-graph/) connections (related entities)
- [Intelligence](../intelligence/) sections (gossip, facts, Good Score for people)
- Streaming availability (for movies and series)
- Image and biographical data where available

Entity pages are programmatically generated -- not manually authored. Data quality determines page quality, which is why [enrichment](../entity-database/data-sources.md) and [quality scoring](../intelligence/richness-scoring.md) are critical.

### Hub Pages
Category landing pages with search, filtering, and browsable entity listings:

- [Companies hub](https://dropthe.org/companies/) -- Browse 400K+ corporations
- [People hub](https://dropthe.org/people/) -- Browse 500K+ individuals
- [Movies hub](https://dropthe.org/movies/) -- Browse 300K+ films
- [Series hub](https://dropthe.org/series/) -- Browse 150K+ shows
- [Games hub](https://dropthe.org/games/) -- Browse 200K+ titles
- [Crypto hub](https://dropthe.org/crypto/) -- Browse 80K+ tokens

### Articles
Data-driven journalism published through the [content pipeline](../pipeline/). Articles live under category-specific paths:

- `/gaming/{slug}/` -- Gaming analysis
- `/crypto/{slug}/` -- Crypto analysis
- `/travel/{slug}/` -- Country and travel data
- `/culture/{slug}/` -- Cultural analysis

Read the latest: [dropthe.org/blog/](https://dropthe.org/blog/)

### Guides
Curated reference content organized by topic. Guides pull live data from the entity database and are updated as new data arrives.

- [All guides](https://dropthe.org/guides/) -- Streaming recommendations, studio rankings, country comparisons, and more

### Interactive Pages

- [On This Day](https://dropthe.org/on-this-day/) -- 366 daily pages showing births, deaths, releases, and events for every calendar day
- [Compare](https://dropthe.org/compare/) -- Side-by-side entity comparisons powered by the knowledge graph
- [Search](https://dropthe.org/search) -- Full-text search across 2M+ entities with instant results

## Data Flow

```
External Sources (TMDB, Wikidata, SEC, CoinGecko, etc.)
        ↓
  Enrichment Pipelines (Python)
        ↓
  Local PostgreSQL (working database)
        ↓
  Supabase (production database)
        ↓
  WordPress (rendering engine + CMS)
        ↓
  Cloudflare (CDN + caching)
        ↓
  dropthe.org (user-facing)
```

### Database Layer
[Supabase](https://supabase.com) (PostgreSQL) stores all entity data, knowledge graph links, intelligence facts, and streaming records. Entity pages query Supabase via REST API with multi-tier caching.

### Rendering Layer
WordPress with custom PHP snippets generates HTML from entity data. No traditional WordPress themes or page builders -- every page type has a dedicated rendering template.

### Caching Strategy
Three-layer caching minimizes database load:

1. **WordPress transient cache**: 15-minute entity cache, 30-minute hub cache, 1-hour count cache
2. **Full-page output cache**: 30-minute fresh, 7-day stale-while-revalidate for anonymous visitors
3. **Cloudflare CDN**: Edge caching with cache-control headers (5-minute browser, 1-hour edge for homepage; 24-hour for entity pages)

Result: warm page load times under 500ms for most pages.

### Content Delivery
All static assets (CSS, JS, fonts, images) served through Cloudflare with long-lived cache headers. Homepage CSS and JS are externalized into cacheable files rather than inlined.

## SEO Architecture

### Indexing Strategy
Not all 2M+ entity pages are submitted to search engines. A tiered indexing strategy focuses crawl budget:

- **Indexed**: S, A, and B tier entities (based on Wikipedia pageview popularity)
- **Not indexed**: C and D tier entities (still publicly accessible, but `noindex` prevents search engine indexing)

This ensures Google spends crawl budget on pages with the best data, not thin pages.

### Sitemaps
Entity sitemaps are generated from the database and include:
- People sitemap (S/A tier)
- Movies sitemap (50K+, 3 sub-sitemaps)
- Series sitemap (49K+, 2 sub-sitemaps)
- Companies sitemap (19K+)
- Games sitemap (50K+)
- On This Day sitemap (493 URLs)
- Article/post sitemaps

### Structured Data
Every page includes schema.org markup:
- `Organization` schema on the homepage
- `Article` + `FAQ` schema on articles
- `WebSite` schema with `SearchAction` for sitelinks search
- Specific entity schemas where applicable

### Internal Linking
Articles contain 18-22 entity links each, connecting editorial content to entity pages. Entity pages link to related entities via the knowledge graph. This creates a dense internal link web that distributes authority across the site.

## Open Data

Raw datasets are available for independent research and verification:

- [Kaggle datasets](https://www.kaggle.com/dropthe) -- Structured exports with documentation
- [HuggingFace datasets](https://huggingface.co/DropTheHQ) -- ML-ready entity data
- [GitHub](https://github.com/DropTheOrg) -- Documentation and tools
