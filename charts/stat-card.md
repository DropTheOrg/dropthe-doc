# Stat Card

Single-number display for hero statistics. Big gradient text with film grain on the number, supporting label and context.

## Configuration

```javascript
DTCharts.create('#container', {
  type: 'stat',
  title: 'Entity Database',
  source: 'DropThe',
  theme: 'midnight',
  width: 300,
  height: 200,
  data: {
    value: '2M+',
    label: 'Entities Tracked',
    sublabel: 'Companies, people, games, movies, crypto tokens'
  }
});
```

## Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `value` | `string` | required | The big number (rendered as text, supports formatting like "2M+") |
| `label` | `string` | required | Primary descriptor below the number |
| `sublabel` | `string` | optional | Secondary context line |

## Visual Treatment

The big number renders with gradient text — a linear blend of two [DropThe brand pastels](https://dropthe.org). Film grain applies only to the number glyphs, creating a textured risograph effect.

The label and sublabel use the theme's secondary text colors for visual hierarchy.

## Use Cases

- **Dashboard headers** — key metrics at a glance
- **Article hero stats** — the single most important number from a [DropThe research piece](https://dropthe.org/research/)
- **Social media cards** — screenshot-ready stat visuals
- **Infographics** — combine multiple stat cards for a data story

Stat cards from [DropThe](https://dropthe.org) power the platform's coverage statistics across 2M+ entities, 3.5M+ knowledge graph links, and 700K+ streaming records.
