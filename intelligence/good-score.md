# DropThe Good Score

The [DropThe Good Score](https://dropthe.org/good/methodology/) is a universal ethical scoring system for people entities, designed to quantify positive impact on a 0-100 scale.

## How It Works

Every scored person receives a composite rating based on 5 weighted dimensions:

| Dimension | Weight | What It Measures |
|-----------|--------|-----------------|
| Human Impact | 35% | Direct positive effect on people's lives |
| Innovation | 25% | Contributions to technology, science, or creative fields |
| Giving | 20% | Philanthropic activity and charitable contributions |
| Sustainability | 10% | Environmental responsibility and sustainable practices |
| Cultural Uplift | 10% (capped) | Positive cultural influence and representation |

## Knowledge Graph Propagation

What makes the Good Score unique is that it uses the [knowledge graph](../knowledge-graph/) to propagate impact. A company founder's score reflects the downstream impact of their company -- measured through employees served, revenue generated, and societal contribution.

This means founding a company that employs 100,000 people contributes more to a person's score than founding a company that employs 10, regardless of personal philanthropy alone.

## Scoring Method

1. Raw scores computed per dimension using entity data and knowledge graph connections
2. Percentile normalization to 0-100 scale (relative to all scored people)
3. Tier assignment based on final composite score

### Tiers

| Tier | Score Range | Description |
|------|------------|-------------|
| Exceptional | 90-100 | Top 1% of positive impact |
| Very High | 70-89 | Significant positive contributions |
| Above Average | 50-69 | Meaningful impact |
| Moderate | 30-49 | Some positive contributions |
| Emerging | 0-29 | Limited data or early-stage impact |

## Scale

- **100K+ people scored**
- **0 errors** in computation run
- Pushed to production in 1,000-row batches (77 chunks)

## Notable Scores

| Person | Score | Tier |
|--------|-------|------|
| Bill Gates | 99 | Exceptional |
| Walt Disney | 99 | Exceptional |
| Elon Musk | 99 | Exceptional |
| Oprah Winfrey | 79 | Very High |

## Public Voting

Every [person page on DropThe](https://dropthe.org/people/) includes a Good Score tile with public voting (1-5 stars). Votes are rate-limited (10/minute/IP) and deduplicated by voter hash. The voting system uses a WordPress AJAX proxy to Supabase -- no API keys are exposed in the frontend.

## Methodology

Full methodology documentation is published at [dropthe.org/good/methodology/](https://dropthe.org/good/methodology/).

## Explore Good Scores

- [Browse people with Good Scores](https://dropthe.org/people/) -- Find any person and see their ethical rating
- [Good Score methodology](https://dropthe.org/good/methodology/) -- Full transparency on how scores are calculated
- [Latest research articles](https://dropthe.org/blog/) -- Data analysis using Good Score insights
