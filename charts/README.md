# DropThe Charts

A canvas-based data visualization library built for the [DropThe](https://dropthe.org) platform. Designed for speed, brand consistency, and embeddability.

Every chart renders on `<canvas>` with a distinctive pastel risograph aesthetic — lava lamp gradients, film grain textures, and rounded geometry. No SVG, no DOM overhead, no dependencies.

## Why We Built It

Most charting libraries optimize for flexibility. DropThe Charts optimizes for **identity**. Every chart screenshot, every embed, every share carries the DropThe visual signature and source attribution baked into the canvas itself.

When a chart from DropThe appears on social media, in a blog post, or embedded on another site — you know where it came from.

## Design System

| Element | Treatment |
|---------|-----------|
| **Colors** | Pastel risograph palette derived from [DropThe brand tokens](https://dropthe.org) |
| **Gradients** | Lava lamp / mesh gradient fills — overlapping radial blobs, not flat linear |
| **Grain** | Film grain applied to chart elements only (not background) |
| **Bars** | Always rounded corners |
| **Highlight mode** | Featured data point gets full lava+grain treatment; others go glass/translucent |
| **Typography** | Space Grotesk (headings), SF Mono (source attribution) |
| **Themes** | Midnight (`#0a0a0f`) and Sand (`#ebe5d9`) — same vibrant colors on both |
| **Attribution** | `Source: DropThe | dropthe.org` watermark rendered into every canvas |

## Chart Types

- [Bar Chart](bar-chart.md) — Vertical bars with lava gradient fills
- [Horizontal Bar Chart](horizontal-bar-chart.md) — Horizontal layout, ideal for rankings and comparisons
- [Line Chart](line-chart.md) — Area fill with gradient, smooth or stepped
- [Stat Card](stat-card.md) — Single big number with gradient text and grain

## Quick Start

```html
<div id="chart"></div>
<script src="https://dropthe.org/wp-content/cache/dt/dt-charts.min.js"></script>
<script>
DTCharts.create('#chart', {
  type: 'bar',
  title: 'Top Game Studios by Metacritic Average',
  subtitle: 'Based on 2M+ reviews across 150K+ titles',
  source: 'DropThe',
  theme: 'midnight',
  data: {
    labels: ['FromSoftware', 'Nintendo', 'Naughty Dog', 'Rockstar', 'id Software'],
    values: [89.2, 87.1, 86.8, 85.3, 84.7],
    highlight: [true, false, false, false, false]
  }
});
</script>
```

## Embed Widget

Drop this snippet into any page to render a DropThe chart:

```html
<div data-dt-chart='{
  "type": "hbar",
  "title": "Streaming Platform Market Share",
  "source": "DropThe",
  "theme": "midnight",
  "data": {
    "labels": ["Netflix", "Disney+", "Amazon", "HBO Max", "Apple TV+"],
    "values": [23.4, 18.1, 12.8, 9.2, 6.1]
  }
}'></div>
<script src="https://dropthe.org/wp-content/cache/dt/dt-charts.min.js"></script>
```

Every embedded chart includes source attribution. No way to remove it — it is part of the canvas render.

## Themes

### Midnight
Dark background (`#0a0a0f`). Vibrant pastel gradients pop against the dark surface. Ideal for social media screenshots and dark-mode sites.

### Sand
Warm light background (`#ebe5d9`). Same vibrant pastels — no muted variants. Works for print-style layouts and light-mode sites.

Both themes use identical color palettes. The brand identity stays consistent regardless of context.

## Brand Colors

| Vertical | Token | Pastel |
|----------|-------|--------|
| Gaming | `#8b5cf6` | `#c4b5fd` |
| Tech | `#3b82f6` | `#93b8fd` |
| Money | `#22c55e` | `#86efac` |
| Culture | `#ec4899` | `#f9a8d4` |
| Coin | `#f59e0b` | `#fdd08a` |
| Gear | `#f97316` | `#fdba74` |
| Travel | `#069494` | `#5eead4` |
| Health | `#E63946` | `#fca5a5` |

## Performance

- **15KB** minified bundle (esbuild)
- **Zero dependencies** — pure canvas API
- **60fps** animation with cubic easing
- Renders in under 16ms on modern hardware
- No DOM manipulation after initial canvas creation

## Open Source

DropThe Charts is part of the [DropThe](https://dropthe.org) data platform. Built with TypeScript, compiled with esbuild.

Repository: [github.com/DropTheOrg/dropthe-charts](https://github.com/DropTheOrg/dropthe-charts)
