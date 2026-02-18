# Data Quality

Maintaining data quality at the scale of [2 million entities](https://dropthe.org) requires automated detection and correction pipelines.

## Quality Sweeps

Regular data quality sweeps catch and fix systematic issues:

### Deduplication
- **TMDB dedup**: 19,339 duplicate groups identified, 24,492 entities merged into primaries
- **Link transfer**: 25,901 links preserved from merged duplicates
- **Data preservation**: 160,988 data fields gained from duplicate records (richer duplicates donated data to primaries)

### Slug Canonicalization
- 155,179 movie slugs + 836 series slugs rebuilt to consistent `name-year` format
- 8,164 numbered slugs (e.g., `name-2`) cleaned to canonical base form
- 3 QID-based slugs corrected

### Garbage Data Removal
| Issue | Records Fixed |
|-------|---------------|
| URLs in date fields (first_aired) | 21,761 |
| URLs in date fields (release_date) | 76 |
| URLs in date fields (death_date) | 2 |
| Orphan links (no valid target) | 1,534 |
| Self-referential links | 285 |
| Junk descriptions | 2,153 |
| Junk bios | 25 |
| Invalid birthdays | 558 |
| Impossible dates | 1 |
| HTML in text fields | 2,142 |
| NaN/Infinity values | 33 |

### Zodiac Cleanup
256,494 people with January 1 birthdays (fake/default dates) had their zodiac signs removed. This corrected a massive skew: Capricorn dropped from 347K (24.5% of all people) to 91K (in line with other signs at ~95K each).

## Richness Scoring

Every entity receives a richness score (0-100) based on data completeness for its type. Scores drive enrichment priority -- entities with low scores and high popularity get enriched first.

| Entity Type | Average Richness | % Rated "Good" (30+) |
|-------------|-----------------|----------------------|
| Series | 44.6 | ~75% |
| Movies | 44.8 | ~75% |
| Games | 44.5 | ~10% |
| Crypto | 49.2 | ~60% |
| Companies | 28.3 | ~30% |
| People | 25.7 | ~4% |

244,995 richness scores calculated and maintained via local PostgreSQL pipeline.

## Bidirectional Link Integrity

The [knowledge graph](../knowledge-graph/) enforces bidirectional consistency. If "Person A works at Company B" exists, the reverse "Company B employs Person A" must also exist. A repair sweep created 11,046 missing reverse links.

## Monitoring

Data quality checks run as part of regular site audits. Issues are logged, prioritized by severity, and fixed in batch operations. All fixes are verified by count comparison before and after execution.

Learn more about [how the knowledge graph maintains quality](../knowledge-graph/how-it-works.md).
