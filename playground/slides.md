---
theme: seriph
background: https://unsplash.com
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: slide-left
mdc: true
# 開発中のアドオンを指定
addons:
  - slidev-addon-google-charts
---

# Google Charts Addon Playground

Welcome to the development & demo slides for `slidev-addon-google-charts`.

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10" style="color: #42b883">
    Press Space to see charts <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: default
---

# 1. Timeline Chart (Non-corechart)

アドオンの `type="Timeline"` が正しくパッケージを解決して描画できるかテストします。

<GoogleChart 
  type="Timeline"
  height="300px"
  :data="[
    [ { type: 'string', id: 'Position' }, { type: 'string', id: 'Name' }, { type: 'date', id: 'Start' }, { type: 'date', id: 'End' } ],
    [ 'President', 'George Washington', new Date(1789, 3, 30), new Date(1797, 2, 4) ],
    [ 'President', 'John Adams', new Date(1797, 2, 4), new Date(1801, 2, 4) ],
    [ 'President', 'Thomas Jefferson', new Date(1801, 2, 4), new Date(1809, 2, 4) ]
  ]"
/>

---

# 2. Gauge Chart (Non-corechart)

アドオンの `type="Gauge"` と、`options`（カラーゾーン指定など）のリアクティブな適用をテストします。

<div class="grid grid-cols-2 gap-4">
<div>

```markdown
<GoogleChart 
  type="Gauge"
  height="220px"
  :data="[
    ['Label', 'Value'],
    ['Memory', 80],
    ['CPU', 55]
  ]"
  :options="{
    redFrom: 90, redTo: 100,
    yellowFrom:75, yellowTo: 90
  }"
/>
```

</div>
<div class="flex justify-center items-center">

<GoogleChart 
  type="Gauge"
  height="220px"
  :data="[
    ['Label', 'Value'],
    ['Memory', 80],
    ['CPU', 55]
  ]"
  :options="{
    redFrom: 90, redTo: 100,
    yellowFrom:75, yellowTo: 90,
    minorTicks: 5
  }"
/>

</div>
</div>

---

# 3. Standard Line Chart (Corechart)

通常の折れ線グラフ（デフォルトの `corechart` パッケージ）が問題なく動くか確認します。

<GoogleChart 
  type="LineChart"
  height="300px"
  :data="[
    ['Year', 'Sales', 'Expenses'],
    ['2023',  1000,      400],
    ['2024',  1170,      460],
    ['2025',  660,       1120],
    ['2026',  1030,      540]
  ]"
  :options="{
    curveType: 'function',
    legend: { position: 'bottom' }
  }"
/>
