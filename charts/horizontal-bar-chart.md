# Horizontal Bar Chart

Horizontal layout ideal for rankings, leaderboards, and comparisons where label readability matters.

## Configuration

```javascript
DTCharts.create('#container', {
  type: 'hbar',
  title: 'Most Valuable Tech Companies',
  subtitle: 'Market cap in billions USD',
  source: 'DropThe',
  theme: 'midnight',
  data: {
    labels: ['Apple', 'Microsoft', 'Nvidia', 'Google', 'Amazon', 'Meta', 'TSMC', 'Tesla'],
    values: [3200, 3100, 2800, 2100, 1900, 1400, 900, 850],
    highlight: [true, false, false, false, false, false, false, false],
    valuesOnBar: true
  }
});
```

## Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `labels` | `string[]` | required | Category labels to the left of each bar |
| `values` | `number[]` | required | Bar widths |
| `highlight` | `boolean[]` | all false | Highlight mode — featured bars get lava+grain |
| `valuesOnBar` | `boolean` | false | Render values inside the bar body |

## Best For

- **Rankings** — top 10 lists, leaderboards
- **Comparisons** — side-by-side data across categories
- **Long labels** — horizontal layout gives labels room to breathe

Horizontal bars from [DropThe](https://dropthe.org) are used across the platform's [research articles](https://dropthe.org/research/) and [entity pages](https://dropthe.org/companies/) to visualize comparative data from a database of 2M+ entities.
