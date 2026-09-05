# slidev-addon-google-charts

A [Slidev](https://sli.dev) addon to integrate **Google Charts** into your presentations. It supports `corechart` packages as well as advanced charts like `Timeline`, `Gauge`, and more.

## Installation

Install the addon into your Slidev project using your preferred package manager:

```bash
# npm (Recommended for general users)
npm install ktkr3d/slidev-addon-google-charts

# pnpm
pnpm add github:ktkr3d/slidev-addon-google-charts

# yarn
yarn add ktkr3d/slidev-addon-google-charts
```

## Setup

Add the addon name to your `slides.md` Frontmatter (the top section of your slides):

```markdown
---
theme: default
addons:
  - slidev-addon-google-charts
---
```

## Usage

You can use the `<GoogleChart />` component in your slides.

### Example 1: Timeline Chart (Non-corechart)

```markdown
<GoogleCharts 
  type="Timeline"
  height="250px"
  :data="[
    [ { type: 'string', id: 'Room' }, { type: 'string', id: 'Name' }, { type: 'date', id: 'Start' }, { type: 'date', id: 'End' } ],
    [ 'Room A', 'Kickoff Meeting', new Date(2026, 8, 5, 10, 0), new Date(2026, 8, 5, 11, 0) ]
  ]"
/>
```

### Example 2: Gauge Chart

```markdown
<GoogleCharts 
  type="Gauge"
  height="200px"
  :data="[
    ['Label', 'Value'],
    ['CPU', 55]
  ]"
  :options="{
    redFrom: 90, redTo: 100,
    yellowFrom: 75, yellowTo: 90
  }"
/>
```

## Properties

| Property | Type | Default | Description |
| --- | --- | --- | --- |
| `type` | `String` | *(Required)* | Chart type (e.g., `LineChart`, `Timeline`, `Gauge`) |
| `data` | `Array` | *(Required)* | The data matrix to draw the chart |
| `options` | `Object` | `{}` | Google Charts configuration options |
| `width` | `String` | `'100%'` | Width of the chart element |
| `height` | `String` | `'400px'` | Height of the chart element |

## Development

If you want to clone this repository and modify the addon:

1. Clone this repository
2. Run `npm install` at the root
3. Start the playground to test your changes: `npm run dev -w playground`

## License

[MIT](./LICENSE)
