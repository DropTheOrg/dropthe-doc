# Bar Chart

Vertical bar chart with lava lamp gradient fills, rounded corners, and optional highlight mode.

## Configuration

```javascript
DTCharts.create('#container', {
  type: 'bar',
  title: 'Company Revenue Growth',
  subtitle: 'Year-over-year percentage change',
  source: 'DropThe',
  theme: 'midnight',    // 'midnight' or 'sand'
  width: 600,           // optional, defaults to container width
  height: 400,          // optional, defaults to 400
  animate: true,        // optional, defaults to true
  data: {
    labels: ['Apple', 'Google', 'Microsoft', 'Amazon', 'Meta'],
    values: [12.3, 8.7, 15.1, 9.8, 22.4],
    highlight: [false, false, false, false, true],  // optional
    valuesOnBar: true   // optional, show values inside bars
  }
});
```

## Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `labels` | `string[]` | required | Category labels below each bar |
| `values` | `number[]` | required | Bar heights |
| `highlight` | `boolean[]` | all false | When true, that bar gets full lava+grain; others go glass/translucent |
| `valuesOnBar` | `boolean` | false | Render values inside the bar body |

## Highlight Mode

Set `highlight: [true]` on any data point to focus viewer attention. The highlighted bar renders with full lava lamp gradient and grain texture. All other bars become translucent glass — visible but de-emphasized.

This is the signature [DropThe](https://dropthe.org) storytelling technique: every chart has a protagonist.

## Gradient System

Each bar gets a unique lava lamp fill generated from overlapping radial gradient blobs. The blob positions are deterministic per bar index — same data always produces the same visual. No two bars look identical, but the palette stays cohesive.

Colors are drawn from the [DropThe brand palette](https://dropthe.org) — pastel risograph versions of the platform's vertical accent colors.

## Export

```javascript
const chart = DTCharts.create('#container', config);
const pngDataUrl = chart.toPNG();  // base64 PNG string
```

Every exported image includes the `Source: DropThe | dropthe.org` attribution rendered into the canvas.
