# Line Chart

Area-fill line chart with gradient shading, smooth curves, and the DropThe grain texture on the fill region.

## Configuration

```javascript
DTCharts.create('#container', {
  type: 'line',
  title: 'Monthly Active Users',
  subtitle: 'Platform growth over 12 months',
  source: 'DropThe',
  theme: 'midnight',
  data: {
    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    values: [1200, 1800, 2400, 3100, 4200, 5800, 7200, 9100, 11400, 14200, 17800, 22100]
  }
});
```

## Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `labels` | `string[]` | required | X-axis labels |
| `values` | `number[]` | required | Y-axis values |

## Visual Treatment

The line uses the gaming pastel (`#c4b5fd`) as the stroke color. The area below fills with a vertical gradient — opaque at the line, fading to transparent at the baseline.

Grid lines render in the theme's grid color. Data points are marked with small filled circles.

Grain texture applies to the filled area only, giving the chart a risograph print quality that matches the [DropThe](https://dropthe.org) visual identity across all chart types.
