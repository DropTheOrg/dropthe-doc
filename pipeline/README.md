# Content Pipeline

[DropThe](https://dropthe.org) operates an automated content pipeline that produces data-driven articles at scale. The system combines AI generation with structured entity data to create research-backed content.

## Architecture

The pipeline follows a 7-step chain:

```
Topic Intelligence → Strategy Brief → Data Pull → Article Writing → Image Selection → WordPress Publish → Post-Publish Audit
```

### Step 1: Topic Intelligence
Automated analysis identifies high-value topics based on search trends, coverage gaps in the entity database, and content calendar planning. Three pitch sessions run daily, each producing 5 article topic proposals.

### Step 2: Strategy Brief
Each approved topic gets a strategy brief defining: thesis statement, fil rouge (narrative thread), pattern break (surprising data point), portable fact (shareable insight), target entity links, and SEO parameters.

### Step 3: Data Pull
The pipeline queries the [entity database](../entity-database/) and [knowledge graph](../knowledge-graph/) for relevant data. Entity links are matched using local PostgreSQL with fuzzy search capability.

### Step 4: Article Writing
Multi-AI strategy: first pass generates data-rich content structure, second pass applies editorial voice. Two different model families are used for AI detection resistance. Articles average 1,400-2,000 words with 18-22 entity links each.

### Step 5: Image Selection
Stock image search via Unsplash and Pexels APIs with API-compliant attribution. Entity compositor adds branded overlays where appropriate.

### Step 6: WordPress Publish
Automated publishing via WordPress REST API with structured metadata: TLDR, FAQ schema, entity cards, companion sidebar data, and category assignment.

### Step 7: Post-Publish Audit
Automated verification checks: HTTP 200 response, entity link resolution, schema markup validation, image loading, and mobile rendering.

## Quality Controls

See [Quality Standards](quality-standards.md) for the full checklist applied to every article.

## Output

Published articles appear at [dropthe.org](https://dropthe.org) with:
- Data-backed claims with entity links to source pages
- Structured schema markup (Article, FAQ, Review where applicable)
- TLDR section optimized for AI answer engines (AEO)
- Companion sidebar with scroll-morphing stages (Quick Answer, TLDR, Gossip, Take)
- Social distribution queued across X, Bluesky, and other platforms
