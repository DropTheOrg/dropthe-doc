# Quality Standards

Every article published on [DropThe](https://dropthe.org) passes through automated and editorial quality checks.

## Automated Checks

| Check | Requirement |
|-------|-------------|
| Word count | Minimum 600, target 1,400-2,000 |
| Entity links | Minimum 10, target 18-22 |
| HTTP status | Published URL returns 200 |
| Schema markup | Valid Article schema present |
| TLDR section | Present, 5 short bullets for AEO |
| FAQ section | Present with structured FAQ schema |
| Image | Featured image set and loading |
| Mobile rendering | Companion sidebar degrades to inline blocks |

## Editorial Standards

### Data Integrity
- Claims backed by entity database numbers
- No invented statistics
- Sources cited in article footer
- Entity links resolve to live pages

### Voice
- No throat-clearing ("In today's world...", "It's worth noting...")
- No summary endings ("In conclusion...")
- Short sentences (10-15 word average)
- Numbers speak -- use them

### Legal
- No defamation
- No insults to public figures
- AI authorship always disclosed
- Never claim to have tested products
- Use: researched, analyzed, compared, reviewed specs

### SEO
- Target keyword in title and first paragraph
- Meta description under 160 characters
- Clean URL slug
- Internal links to relevant entity pages
- Structured data (Article, FAQ, Review schemas)

## Companion Sidebar

Desktop articles (>1024px) feature a scroll-morphing sticky sidebar with 4 progressive stages:

| Stage | Scroll % | Content |
|-------|----------|---------|
| Quick Answer | 0-15% | Direct answer to the article's question |
| TLDR | 15-40% | 5-bullet summary optimized for AI engines |
| Drop The Gossip | 40-80% | Related entity facts from the knowledge graph |
| Drop The Take | 80-100% | Editorial perspective backed by data |

On mobile, all stages render as inline blocks within the article flow.
