---
# ==========================================
# 🔖 THEME : テーマ
# ==========================================
theme: default
background: ''
class: text-center
lineNumbers: false
drawings:
  persist: false
title: Slidev Addon Google Charts
addons:
  - slidev-addon-google-charts

# ==========================================
# 📍 COVER : NEO-ARCH SYSTEMS
# ==========================================
layout: cyber-cover
highlighter: shiki
transition: fade
---

::command::
guest@wired.net ~ $ npx slidev ./presentation.md

::default::
SLIDEV ADDON GOOGLE CHARTS

::subtitle::
Add interactive Google Charts to your Slidev.

---
# ==========================================
# 📌 SLIDE : 01. Introduction
# ==========================================
layout: cyber-one-col
---

::header::
## 01. Introduction

::default::
[Slidev](https://sli.dev/)はMarkdownでスライドを作成できる開発者向けのWebベースプレゼンテーションツールです。

- テキストファイルにMarkdown形式で書き込むだけで簡単にスライドを構築できます
- HTMLやVueコンポーネントを埋め込み、インタラクティブで動きのある表現が可能です
- 綺麗なコードハイライト、PDFエクスポート、ライブコーディングなどを標準搭載しています

<br>

Slidevで[Google Charts](https://developers.google.com/chart/)を利用するためのアドオン [**<span class="point">slidev-addon-google-charts</span>**](https://github.com/ktkr3d/slidev-addon-google-charts/) を作成しました。

- Google Chartsの様々な種類のチャートに対応しています
- スライド表示中に対話的な操作が可能です
- アドオンを`npm install`で導入できます

---
# ==========================================
# 📌 SLIDE : 02. SETUP
# ==========================================
layout: cyber-two-cols
---

::header::
## 02. SETUP

::left::

1. プロジェクトフォルダを作成します

```bash
mkdir slidev-workspace
cd slidev-workspace
```

2. Slidevを初期化します

```bash
npm init -y && npm install @slidev/cli
```

3. アドオンをインストールします

```bash
npm install -allow-git=root \
    ktkr3d/slidev-addon-google-charts
```

::right::
<br>

<ul class="cyber-list text-lg">
  <li><strong>slidev-workspace</strong> — プロジェクトフォルダ</li>
</ul>

<br><br><br>

<ul class="cyber-list text-lg">
  <li><strong>@slidev/cli</strong> — Slidev パッケージ</li>
</ul>

<br><br>

<ul class="cyber-list text-lg">
  <li><strong>slidev-addon-google-charts</strong> — アドオン</li>
</ul>

---
# ==========================================
# 📌 SLIDE : 03. HOW TO USE
# ==========================================
layout: cyber-two-cols
---

::header::
## 03. HOW TO USE

::left::

```vue
<GoogleCharts 
  type="GeoChart"
  :options="{
    region: 'JP',
    resolution: 'provinces',
  }"
  :data="[
    ['都道府県', '値'],
    ['北海道', 100]
  ]"
/>
```

::right::

<ul class="cyber-list text-lg">
  <li><strong>GoogleCharts</strong> — コンポーネント名</li>
  <li><strong>type</strong> — チャート種別</li>
  <li><strong>:options</strong> — オプション</li>
  <li><strong>:data</strong> — データ</li>
</ul>

---
# ==========================================
# 📌 SLIDE : 04. CHART TYPE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 04. CHART TYPE

::left::

- CoreChart
  - AreaChart
  - BarChart
  - BubbleChart
  - CandlestickChart
  - ColumnChart
  - ComboChart
  - PieChart
  - ScatterChart
  - SteppedAreaChart

::right::
 
- AnnotationChart 注釈付きタイムライン
- Calendar
- Gantt ガントチャート
- Gauge
- GeoChart
- Map Google マップ地図表示
- Orgchart 組織図
- Sankey サンキー・ダイアグラム
- Table データ表
- Timeline スケジュールタイムライン
- TreeMap ツリーマップ
- WordTree テキストワードツリー

---
# ==========================================
# 📌 SLIDE : 05. CORECHART - PIECHART
# ==========================================
layout: cyber-two-cols
---

::header::
## 05. CORECHART - [PIECHART](https://developers.google.com/chart/interactive/docs/gallery/piechart)

::left::

```vue
<GoogleCharts 
  type="PieChart"
  :options="{ title: 'My Daily Activities' }"
  :data="[
    ['Task', 'Hours per Day'],
    ['Work',     11],
    ['Commute',  4],
    ['Sleep',    9]
  ]"
/>
```

::right::

<GoogleCharts 
  type="PieChart"
  :options="{
    title: 'My Daily Activities'
  }"
  :data="[
    ['Task', 'Hours per Day'],
    ['Work',     11],
    ['Commute',  4],
    ['Sleep',    9]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 06. CORECHART - LINECHART
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 06. CORECHART - [LINECHART](https://developers.google.com/chart/interactive/docs/gallery/linechart)

::left::

<GoogleCharts 
  type="LineChart"
  :options="{
    title: 'Company Performance',
    curveType: 'function',
    legend: { position: 'bottom' }
  }"
  :data="[
    ['Year', 'Sales', 'Expenses'],
    ['2004',  1000,      400],
    ['2005',  1170,      460],
    ['2006',  660,       1120],
    ['2007',  1030,      540]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 07. CORECHART - (UNTESTED)
# ==========================================
layout: cyber-two-cols
---

::header::
## 07. CORECHART - (UNTESTED)

::left::

- CoreChart
  - AreaChart
  - BarChart
  - BubbleChart
  - CandlestickChart
  - ColumnChart
  - ComboChart
  - ScatterChart
  - SteppedAreaChart

::right::

---
# ==========================================
# 📌 SLIDE : 08. ANNOTATIONCHART
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 08. [ANNOTATIONCHART](https://developers.google.com/chart/interactive/docs/gallery/annotationchart)

::left::

<GoogleCharts 
  type="AnnotationChart"
  :options="{
    displayAnnotations: true
  }"
  :data="[
    ['Date',  'Kepler-22b mission', 'Kepler title', 'Kepler text', 'Gliese 163 mission', 'Gliese title', 'Gliese text'],
    [new Date(2314, 2, 15), 12400, undefined, undefined,
                            10645, undefined, undefined],
    [new Date(2314, 2, 16), 24045, 'Lalibertines', 'First encounter',
                            12374, undefined, undefined],
    [new Date(2314, 2, 17), 35022, 'Lalibertines', 'They are very tall',
                            15766, 'Gallantors', 'First Encounter'],
    [new Date(2314, 2, 18), 12284, 'Lalibertines', 'Attack on our crew!',
                            34334, 'Gallantors', 'Statement of shared principles'],
    [new Date(2314, 2, 19), 8476, 'Lalibertines', 'Heavy casualties',
                            66467, 'Gallantors', 'Mysteries revealed'],
    [new Date(2314, 2, 20), 0, 'Lalibertines', 'All crew lost',
                            79463, 'Gallantors', 'Omniscience achieved']
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 09. CALENDAR
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 09. [CALENDAR](https://developers.google.com/chart/interactive/docs/gallery/calendar)

::left::

<!--
<GoogleCharts 
  type="Calendar"
  :options="{
    title: 'Red Sox Attendance',
    height: 350
  }"
  :data="[
    [ 'Date', 'Won/Loss' ],
    [ new Date(2012, 3, 13), 37032 ],
    [ new Date(2012, 3, 14), 38024 ],
    [ new Date(2012, 3, 15), 38024 ],
    [ new Date(2012, 3, 16), 38108 ],
    [ new Date(2012, 3, 17), 38229 ],
    [ new Date(2013, 9, 4), 38177 ],
    [ new Date(2013, 9, 5), 38705 ],
    [ new Date(2013, 9, 12), 38210 ],
    [ new Date(2013, 9, 13), 38029 ],
    [ new Date(2013, 9, 19), 38823 ],
    [ new Date(2013, 9, 23), 38345 ],
    [ new Date(2013, 9, 24), 38436 ],
    [ new Date(2013, 9, 30), 38447 ]
  ]"
/>
-->
::right::

<p class="alert">Concerns regarding load</p>

---
# ==========================================
# 📌 SLIDE : 10. GANNT
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 10. [GANNT](https://developers.google.com/chart/interactive/docs/gallery/gannt)

::left::

<GoogleCharts 
  type="Gantt"
  :options="{
    width: 500,
    height: 250
  }"
  :data="[
    [ 'Task ID', 'Task Name', 'Resource', 'Start', 'End', 'Duration', 'Percent Complete', 'Dependencies' ],
    ['Research', 'Find sources', null, new Date(2015, 0, 1), new Date(2015, 0, 5), 0,  100,  null],
    ['Write', 'Write paper', 'write', null, new Date(2015, 0, 9), 259200000, 25, 'Research,Outline'],
    ['Cite', 'Create bibliography', 'write', null, new Date(2015, 0, 7), 86400000, 20, 'Research'],
    ['Complete', 'Hand in paper', 'complete', null, new Date(2015, 0, 10), 86400000, 0, 'Cite,Write'],
    ['Outline', 'Outline paper', 'write', null, new Date(2015, 0, 6), 86400000, 100, 'Research']
  ]"
/>


::right::

---
# ==========================================
# 📌 SLIDE : 11. GAUGE
# ==========================================
layout: cyber-two-cols
---

::header::
## 11. [GAUGE](https://developers.google.com/chart/interactive/docs/gallery/gauge)

::left::

```vue
<GoogleCharts 
  type="Gauge"
  :data="[
    ['Label', 'Value'],
    ['CPU', 85]
  ]"
/>
```

::right::

<GoogleCharts 
  type="Gauge"
  :data="[
    ['Label', 'Value'],
    ['CPU', 85]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 12. GEOCHART
# ==========================================
layout: cyber-two-cols
---

::header::
## 12. [GEOCHART](https://developers.google.com/chart/interactive/docs/gallery/geochart)

::left::

```vue
<GoogleCharts 
  type="GeoChart"
  :options="{
    region: 'JP',
    resolution: 'provinces',
  }"
  :data="[
    ['都道府県', '値'],
    ['北海道', 100]
  ]"
/>
```

::right::

<GoogleCharts 
  type="GeoChart"
  :options="{
    region: 'JP',
    resolution: 'provinces',
  }"
  :data="[
    ['都道府県', '値'],
    ['北海道', 100]
  ]"
/>


---
# ==========================================
# 📌 SLIDE : 13. MAP
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 13. [MAP](https://developers.google.com/chart/interactive/docs/gallery/map)

::left::

<GoogleCharts 
  type="Map"
  :options="{
    showTooltip: true,
    showInfoWindow: true,
    width: 400,
    height: 250
  }"
  :data="[
    ['Country', 'Population'],
    ['China', 'China: 1,363,800,000'],
    ['India', 'India: 1,242,620,000'],
    ['US', 'US: 317,842,000'],
    ['Indonesia', 'Indonesia: 247,424,598'],
    ['Brazil', 'Brazil: 201,032,714'],
    ['Pakistan', 'Pakistan: 186,134,000'],
    ['Nigeria', 'Nigeria: 173,615,000'],
    ['Bangladesh', 'Bangladesh: 152,518,015'],
    ['Russia', 'Russia: 146,019,512'],
    ['Japan', 'Japan: 127,120,000']
  ]"
/>

::right::

<p class="alert">Need a mapsApiKey </p>

---
# ==========================================
# 📌 SLIDE : 14. ORGCHART
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 14. [ORGCHART](https://developers.google.com/chart/interactive/docs/gallery/orgchart)

::left::

<GoogleCharts 
  type="OrgChart"
  :options="{
  }"
  :data="[
    [ 'Name', 'Manager', 'ToolTip' ],
    ['Mike', '', 'The President'],
    ['Jim', 'Mike', 'VP'],
    ['Alice', 'Mike', ''],
    ['Bob', 'Jim', 'Bob Sponge'],
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 15. SANKEY
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 15. [SANKEY](https://developers.google.com/chart/interactive/docs/gallery/sankey)

::left::

<GoogleCharts 
  type="Sankey"
  :options="{
  }"
  :data="[
    [ 'From', 'To', 'Weight' ],
    [ 'A', 'X', 5 ],
    [ 'A', 'Y', 7 ],
    [ 'A', 'Z', 6 ],
    [ 'B', 'X', 2 ],
    [ 'B', 'Y', 9 ],
    [ 'B', 'Z', 4 ]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 16. TABLE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 16. [TABLE](https://developers.google.com/chart/interactive/docs/gallery/table)

::left::

```vue
<GoogleCharts 
  type="Table"
  :options="{ title: 'My Daily Activities' }"
  :data="[
    ['Name',  'Salary', 'Full Time Employee'],
    ['Mike',  {v: 10000, f: '$10,000'}, true],
    ['Jim',   {v:8000,   f: '$8,000'},  false],
    ['Alice', {v: 12500, f: '$12,500'}, true],
  ]"
/>
```

::right::

<GoogleCharts 
  type="Table"
  :options="{
    title: 'My Daily Activities',
    showRowNumber: true,
    width: 400,
    height: 150
  }"
  :data="[
    ['Name',  'Salary', 'Full Time Employee'],
    ['Mike',  {v: 10000, f: '$10,000'}, true],
    ['Jim',   {v:8000,   f: '$8,000'},  false],
    ['Alice', {v: 12500, f: '$12,500'}, true],
  ]"
/>


---
# ==========================================
# 📌 SLIDE : 17. TIMELINE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 17. [TIMELINE](https://developers.google.com/chart/interactive/docs/gallery/timeline)

::left::

<GoogleCharts 
  type="Timeline"
  :options="{
    width: '100%'
  }"
  :data="[
    [ 'President', 'Start', 'End' ],
    [ 'Washington', new Date(1789, 3, 30), new Date(1797, 2, 4) ],
    [ 'Adams',      new Date(1797, 2, 4),  new Date(1801, 2, 4) ],
    [ 'Jefferson',  new Date(1801, 2, 4),  new Date(1809, 2, 4) ]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 18. TREEMAP
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 18. [TREEMAP](https://developers.google.com/chart/interactive/docs/gallery/treemap)

::left::

<GoogleCharts 
  type="TreeMap"
  :options="{
  }"
  :data="[
    ['Location', 'Parent', 'Market trade volume (size)', 'Market increase/decrease (color)'],
    ['Global',    null,                 0,                               0],
    ['America',   'Global',             0,                               0],
    ['Europe',    'Global',             0,                               0],
    ['Asia',      'Global',             0,                               0],
    ['Australia', 'Global',             0,                               0],
    ['Africa',    'Global',             0,                               0],
    ['Brazil',    'America',            11,                              10],
    ['USA',       'America',            52,                              31],
    ['Mexico',    'America',            24,                              12],
    ['Canada',    'America',            16,                              -23],
    ['France',    'Europe',             42,                              -11],
    ['Germany',   'Europe',             31,                              -2],
    ['Sweden',    'Europe',             22,                              -13],
    ['Italy',     'Europe',             17,                              4],
    ['UK',        'Europe',             21,                              -5],
    ['China',     'Asia',               36,                              4],
    ['Japan',     'Asia',               20,                              -12],
    ['India',     'Asia',               40,                              63],
    ['Laos',      'Asia',               4,                               34],
    ['Mongolia',  'Asia',               1,                               -5],
    ['Israel',    'Asia',               12,                              24],
    ['Iran',      'Asia',               18,                              13],
    ['Pakistan',  'Asia',               11,                              -52],
    ['Egypt',     'Africa',             21,                              0],
    ['S. Africa', 'Africa',             30,                              43],
    ['Sudan',     'Africa',             12,                              2],
    ['Congo',     'Africa',             10,                              12],
    ['Zaire',     'Africa',             8,                               10]
  ]"
/>

::right::

<dl>
  <dt>左クリック</dt>
  <dd>末端へ進む</dd>
  <dt>右クリック</dt>
  <dd>上位へ戻る</dd>
</dl>

---
# ==========================================
# 📌 SLIDE : 19. WORDTREE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 19. [WORDTREE](https://developers.google.com/chart/interactive/docs/gallery/wordtree)

::left::

<GoogleCharts 
  type="WordTree"
  :options="{
    width: '100%',
    height: 350,
    wordtree: {
      format: 'implicit',
      word: 'cats'
    }  
  }"
  :data="[
    ['Phrases'],
    ['cats are better than dogs'],
    ['cats eat kibble'],
    ['cats are better than hamsters'],
    ['cats are awesome'],
    ['cats are people too'],
    ['cats eat mice'],
    ['cats meowing'],
    ['cats in the cradle'],
    ['cats eat mice'],
    ['cats in the cradle lyrics'],
    ['cats eat kibble'],
    ['cats for adoption'],
    ['cats are family'],
    ['cats eat mice'],
    ['cats are better than kittens'],
    ['cats are evil'],
    ['cats are weird'],
    ['cats eat mice'],
  ]"/>

::right::

---
# ==========================================
# 📍 COVER : NEO-ARCH SYSTEMS
# ==========================================
layout: cyber-cover
highlighter: shiki
transition: fade
ribbon: TEMPLATE
---

::command::
root@archiso ~ # ./start_presentation

::default::
# NEO-ARCH SYSTEMS

::subtitle::
The Minimalist OS Meets Cyberpunk Aesthetic.

---
# ==========================================
# 📌 SLIDE : 91. PROFILE
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 91. PROFILE

::left::

- **NAME** — [ktkr3d](https://github.com/ktkr3d)
- **OS** — Arch Linux (Hyprland / paru)
- **SHELL** — fish
- **KEYBOARD** — us / jp
- **IDE** - vscode / code-server
- **LANGUAGE** - C++ / JavaScript / Lua
- **WIRED** — <span class="text-xs font-thin tracking-widest uppercase text-neutral-500">everyone_can_connect..._but_not_me.err</span>

::right::

<!-- 💡 アバター画像を綺麗に丸で切り抜くコード -->
<div class="flex flex-col items-center justify-center h-full">
  <div class="w-40 h-40 rounded-full border-2 border-$arch-cyan p-1 bg-black/40 shadow-[0_0_20px_rgba(23,147,209,0.4)] overflow-hidden aspect-square">
    <img 
      src="https://ktkr3d.github.io/images/avatar.png" 
      class="w-full h-full object-cover rounded-full" 
      alt="Avatar"
    />
  </div>
  <p class="text-xs font-mono text-neutral-500 mt-3">STATUS: OFFLINE_LOOPBACK</p>
</div>

---
# ==========================================
# 📌 SLIDE : 92. CYBER LAYOUTS
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 92. LAYOUTS

::default::

| LAYOUT NAME | PURPOSE | PARTITION |
| :--- | :--- | :--- |
| `cyber-cover` | Cover | - `::command::` <br> - `::default::` <br> - `::subtitle::` |
| `cyber-one-col` | One Column | - `::header::` <br> - `::default::` |
| `cyber-two-cols` | Two Columns | - `::header::` <br> - `::left::` <br> - `::right::`|
| `lain-end` | Closing Slide | (none) |

---
# ==========================================
# 📌 SLIDE : 93. FRONT MATTER
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 93. FRONT MATTER

::left::

Head Matter

```yaml
title: Arch Linux Style Presentation
theme: default
addons: [ slidev-addon-google-charts ]
lineNumbers: false
drawings: { persist: false }
highlighter: shiki
transition: fade

layout: cyber-cover
background: ''
class: text-center
```

::right::

Slide Front Matter (One Column)

```yaml
layout: cyber-one-col
```

Slide Front Matter (Two Columns)

```yaml
layout: cyber-two-cols
```

Slide Front Matter (Closing Slide)

```yaml
layout: lain-end
```

---
# ==========================================
# 📌 SLIDE : 94. CYBER TABLE
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 94. TABLE

::default::

<div class="cyber-table">

| MODULE NAME | CORE ARCHITECTURE | INTEGRITY | OPERATIONAL STATUS |
| :--- | :--- | :--- | :--- |
| `kernel-hardened` | Linux x86_64 | 100% SECURE | `ACTIVE (BYPASS_MODE)` |
| `wayland-compositor` | Hyprland / Cyber | 98.4% STABLE | `RENDERING` |
| `luna-network-daemon` | Protocol-X via Wired | 100% ONLINE | `ENCRYPTED_TUNNEL` |

</div>

---
# ==========================================
# 📌 SLIDE : 95. CODEBLOCK
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 95. CODEBLOCK

::left::

```ts
// Retry failed async operation
export async function retry<T>(
  fn: () => Promise<T>,
  retries = 3
): Promise<T> {
  try {
    return await fn();
  } catch (err) {
    if (retries <= 0) throw err;
    console.warn(`Fail: \${retries} left`);
    return retry(fn, retries - 1);
  }
}
```

::right::

<dl>
<dt>Auto-Retry</dt><dd>Automatically re-runs failed async tasks.</dd>
<dt>Type-Safe</dt><dd>Maintains the exact return type for any function.</dd>
<dt>Recursion</dt><dd>Retries clean and minimal with self-calling loops.</dd>
<dt>Safe Throw</dt><dd>Throws the final error after all attempts fail.</dd>
</dl>

---
# ==========================================
# 📌 SLIDE : 96. LIST
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 96. LIST

::left::

Task list

```text
- [X] Closed
- [ ] Open
```
- [X] Closed
- [ ] Open

::right::

Description List

```text
<dl>
  <dt>Real</dt>
  <dd>The real world</dd>
  <dt>Wired</dt>
  <dd>The world of the Internet</dd>
</dl>
```

<dl>
<dt>Real</dt><dd>The real world</dd>
<dt>Wired</dt><dd>The world of the Internet</dd>
</dl>

---
# ==========================================
# 📌 SLIDE : 97. RIBBON / FOOTER
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 97. RIBBON / FOOTER

::left::

RIBBON - TEMPLATE

```yaml
---
ribbon: TEMPLATE
---
```

RIBBON - WIP

```yaml
---
ribbon: WIP
---
```

::right::

FOOTER - Default

```text
```
> LAYER_SLIDETITLE

FOOTER - Custom

```text
::footer::
custom string
```
> custom string

---
# ==========================================
# 📌 SLIDE : 98. DECORATION
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 98. DECORATION

::left::

```html
<span class="point">Point</span>
```

<span class="point">Point</span>

<br>

```html
<span class="alert">Alert</span>
```

<span class="alert">Alert</span>

::right::

---
# ==========================================
# 🔖 CLOSING : END
# ==========================================
layout: lain-end
ribbon: TEMPLATE
---
