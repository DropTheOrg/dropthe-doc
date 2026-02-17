# Richness Scoring

Every entity in the [DropThe database](https://dropthe.org) receives a data completeness score from 0 to 100, measuring how much structured information is available.

## How It Works

Each entity type has a defined set of expected fields with weights. The richness score is the weighted sum of populated fields divided by the maximum possible score.

For example, a movie entity might be scored on:
- Title (required)
- Release date
- Runtime
- Genres
- Overview/description
- Director
- Cast
- Ratings
- Image
- Streaming availability

A movie with all fields populated scores 100. A movie with only title and release date scores much lower.

## Current Scores by Type

| Entity Type | Average Score | % Good (30+) | Entities Scored |
|-------------|--------------|---------------|-----------------|
| Crypto | 49.2 | ~60% | 80,000+ |
| Series | 44.6 | ~75% | 150,000+ |
| Movies | 44.8 | ~75% | 300,000+ |
| Games | 44.5 | ~10% | 200,000+ |
| Companies | 28.3 | ~30% | 400,000+ |
| People | 25.7 | ~4% | 500,000+ |

244,995 entities have been scored and tracked. Scores recalculate locally via PostgreSQL in approximately 22 minutes for a full sweep.

## Driving Enrichment Priority

Richness scores combine with popularity tier (S/A/B/C/D from Wikipedia pageviews) to create a mining priority score:

```
priority = (1 - richness_score/100) * popularity_weight
```

High-popularity, low-richness entities get enriched first. This ensures that the most-visited [entity pages on DropThe](https://dropthe.org) have the best data, while less-visited entities are enriched opportunistically.

## Impact of Enrichment

Before and after TMDB deep enrichment:
- Movies average richness: **18.2 → 44.8** (146% improvement)
- Series average richness: **26.3 → 44.6** (70% improvement)
- 75% of enriched movies now rate "good" (30+ score)

Richness scores are stored in entity metadata (`_richness_score` and `_mining_priority` fields) and updated after each enrichment run.
