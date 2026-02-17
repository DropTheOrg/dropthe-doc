# Name Intelligence

[DropThe](https://dropthe.org) maintains a name intelligence database analyzing 20,925 unique first names extracted from 1.27 million people entities.

## What It Contains

For each first name in the database:

| Field | Description |
|-------|-------------|
| Gender distribution | Male/female/unisex breakdown based on actual entity data |
| Nationality distribution | Which countries this name appears most in |
| Birth decade trends | How name popularity changes across decades |
| Zodiac distribution | Astrological sign patterns for people with this name |
| Notable people | Top 10 most notable people with this name (by Wikipedia pageviews) |

## How It's Built

1. Extract first names from 1.45 million people entities
2. Normalize and deduplicate to 20,925 unique names
3. For each name, aggregate demographics across all matching people
4. Compute distributions using verified data (excluding fake January 1 birthdays)
5. Rank notable people by Wikipedia pageview data

## Applications

Name intelligence powers several features on [dropthe.org](https://dropthe.org):

- **Name pages**: Dedicated pages showing demographics, trends, and notable people for each name
- **Birthday tools**: "Who shares my birthday?" interactive features
- **Demographic analysis**: Data-driven articles about naming trends across cultures and eras

## Coverage

| Metric | Count |
|--------|-------|
| Unique names analyzed | 20,925 |
| People covered | 1,270,000 |
| Coverage rate | 87% of all people entities |
