# Fact Mining

The The [entity intelligence engine](https://dropthe.org) runs 8 automated miners that extract non-obvious facts from entity data and knowledge graph connections.

## Miners

### Zodiac Miner
Assigns zodiac signs to people based on verified birth dates. Includes a cleanup layer that removes zodiac from 256K people with suspicious January 1 birthdays (default/fake dates).

- **Output**: 1,550 facts
- **Example**: "73% of top tech founders are Aquarius or Capricorn"

### Chinese Zodiac Miner
Maps birth years to Chinese zodiac animals for people entities.

- **Output**: 1,390 facts

### Geographic Miner
Clusters entities by location, finding patterns in where notable people come from, where companies cluster, and how geography correlates with industry.

- **Output**: 879 facts
- **Example**: "Helsinki produces 3x more game studio founders per capita than Silicon Valley"

### Birthday Twins Miner
Finds notable people who share exact birth dates, creating unexpected connections across industries and eras.

- **Output**: 295 facts
- **Example**: "Two Nobel Prize winners in Physics shared the same birthday 50 years apart"

### Temporal Miner
Discovers patterns in dates -- what happened on specific days, years with unusual clustering of events, seasonal patterns in releases and births.

- **Output**: 3,143 born_today facts + 141 temporal pattern facts

### Cross-Vertical Bridge Miner
Identifies entities that span multiple categories in unusual ways -- actors who founded tech companies, musicians who invested in crypto, athletes who became politicians.

- **Output**: Growing (compute-intensive)

### Financial Mismatch Miner
Flags companies where financial performance doesn't match public perception or market position.

- **Status**: Running (Supabase timeout handling in progress)

### Co-Star Frequency Miner
Analyzes which actors appear together most frequently across films and series, revealing collaboration patterns in entertainment.

- **Status**: Running (batch size optimization in progress)

## Architecture

Each miner is an independent Python module that:

1. Queries the local PostgreSQL database for relevant entity data
2. Applies analysis logic to find patterns
3. Writes results to the `entity_facts` table with typed metadata
4. Links facts to relevant entities via `fact_entity_links`

Miners run on local infrastructure to avoid production API limits. Results are pushed to production on [DropThe](https://dropthe.org) after verification.

## Collections

Facts are organized into **756 published collections** containing 5,870 items. Collections group related facts for presentation on entity pages and in the [DropThe Gossip](https://dropthe.org) sections.
