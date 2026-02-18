# Data Roadmap

[DropThe](https://dropthe.org) is building the most interconnected entertainment and world data graph on the internet. Here's what's coming.

## The Vision

DropThe is not a movie database. Not a crypto tracker. Not a country stats page. It's a **[knowledge graph](../knowledge-graph/)** where every entity connects to every other entity through data.

The value isn't in having 300K movies -- it's in knowing that the director of Parasite studied at the Korean Academy of Film Arts, which is in South Korea, whose GDP grew 4.2% the year Parasite won Best Picture, while Netflix had 2,847 Korean titles streaming across 30 countries.

Every fact connects to five more facts. That's the graph.

## Current Scale

| Asset | Count |
|-------|-------|
| [Entities](../entity-database/) | 2M+ |
| [Knowledge graph links](../knowledge-graph/) | 3.5M+ |
| [Streaming records](../streaming-data/) | 700K+ |
| Country time-series data points | 342,548 |
| [Games with deep data](https://dropthe.org/games/) | 40K+ (IGDB enriched) |
| [Countries with 160+ fields](https://dropthe.org/countries/) | 246 |

## Phase 1: Completing Current Verticals

### Box Office Data
Budget and revenue data for 40K+ [movies](https://dropthe.org/movies/) via TMDB. Enables ROI analysis, revenue vs GDP correlation, "Most profitable movies per decade" research.

### Awards Data
Oscar, Emmy, BAFTA, Golden Globe, Cannes, Grammy, Pulitzer -- mapped as relationships in the [knowledge graph](../knowledge-graph/). Enables "Universities that produce the most Oscar winners" and "[Countries](https://dropthe.org/countries/) with most Nobel laureates."

### Game Sales & Player Data
Steam player counts, review scores, pricing for 15K+ [games](https://dropthe.org/games/). Enables "Most played games by country" and correlation with internet penetration.

### Crypto Price History
Monthly price, market cap, and volume for top 500 [crypto tokens](https://dropthe.org/crypto/) over 5 years. Enables "Bitcoin vs Gold vs S&P 500" comparisons and "Crypto Market Cap vs Global GDP" analysis.

### Company Financials
Revenue, employees, market cap, and ticker data for 5K+ [companies](https://dropthe.org/companies/). Enables "Biggest gaming companies by revenue" and "Film studios: revenue vs hit movies."

## Phase 2: New Data Domains

### Historical Events
Expanding from 1,800 to 10,000+ events (1900-2025). Wars, politics, science, culture, disasters, sports. Enables "What happened the year you were born?" and timeline pages.

### Music & Albums
Discography data for musicians already in the [people database](https://dropthe.org/people/). ~50K albums via MusicBrainz. Enables "The Soundtrack of 1984" and "Most prolific producers by decade."

### Sports & Olympics
Olympic medals by country (1896-2024), World Cup results, major championships. Enables "Olympic Medal Count vs GDP" and "Does hosting the Olympics boost tourism?"

### Book Awards & Bestsellers
Award data for the 5,700+ books in the database. Enables "Nobel Literature Winners by Country" and "Most adapted books (books to movies)."

## Phase 3: Deep Historical Time-Series

Expanding country data from current World Bank indicators to deep historical datasets:

| Source | Indicators | Time Range | Data Points |
|--------|-----------|------------|-------------|
| Our World in Data | CO2, democracy, energy, poverty, literacy | 1750-2024 | ~5M |
| IMF World Economic Outlook | Debt, fiscal balance, reserves, exchange rates | 1980-2024 | ~1M |
| UNESCO | Education enrollment, R&D spending, researchers | 1970-2024 | ~500K |
| WHO | Disease prevalence, vaccination, health workforce | 1990-2024 | ~500K |
| ILO | Labor participation, wages, working hours | 1990-2024 | ~300K |
| FAO | Food production, crop yields, agricultural land | 1961-2024 | ~300K |
| WIPO | Patent filings by country and sector | 2000-2024 | ~200K |

**Total projected: ~12M new data points**

## How the Graph Connects Everything

```
                    YEAR (1900-2025)
                         |
         +-------+-------+-------+-------+
         |       |       |       |       |
      MOVIES  PEOPLE   GAMES  EVENTS  COUNTRY DATA
         |       |       |              |
      has_actor  educated_at         time_series
         |       |                      |
      PERSON  UNIVERSITY            indicators[]
         |       |                      |
      born_in  located_in              |
         |       |                     |
      COUNTRY---+---------------------+
         |
      has_company
         |
      COMPANY --- developed ---> GAME
```

Every node connects to every other node through at most 3 hops. A [person](https://dropthe.org/people/) connects to a [company](https://dropthe.org/companies/) connects to a [country](https://dropthe.org/countries/) connects to time-series data connects to [movies](https://dropthe.org/movies/) released that year. That's the power of the graph.

## Content This Enables

The enriched graph powers cross-domain analysis that no single-vertical database can produce:

### Economy x Entertainment
- Revenue correlation between [box office](https://dropthe.org/movies/) and GDP
- Gaming industry revenue vs film industry: 20-year race
- Streaming wars by the numbers: who dominates each country

### Geography x Entertainment
- [Countries](https://dropthe.org/countries/) that produce the most game developers
- [Universities](https://dropthe.org/universities/) that shaped Hollywood
- K-Content explosion: South Korea's cultural export vs GDP growth

### People x Data
- The busiest [actors](https://dropthe.org/people/) alive
- Director dynasties: family trees of filmmaking
- University dropout billionaires vs PhD CEOs

### Time x Everything
- "What the World Looked Like When [Movie] Was Released"
- "Born in 1984: Every Person, Movie, Game, and Event From Your Birth Year"
- Country comparison tool: pick any 2 countries, compare everything

Browse current data at [dropthe.org](https://dropthe.org). Follow the latest research on the [DropThe blog](https://dropthe.org/blog/).

## Open Datasets

As enrichment progresses, datasets are published for independent research:

- [Kaggle datasets](https://www.kaggle.com/dropthe)
- [HuggingFace datasets](https://huggingface.co/DropTheHQ)
- [GitHub](https://github.com/DropTheOrg)
