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
# 📌 SLIDE : 01. INTRODUCTION
# ==========================================
layout: cyber-one-col
---

::header::
## 01. INTRODUCTION

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

2. Slidevをインストールします

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

<dl>
  <dt>フォルダ</dt><dd>slidev-workspace</dd>
</dl>

<br><br><br>

<dl>
  <dt>パッケージ</dt><dd>@slidev/cli</dd>
</dl>

<br><br>

<dl>
  <dt>アドオン</dt><dd>slidev-addon-google-charts</dd>
</dl>

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

<dl>
  <dt>GoogleCharts</dt><dd>コンポーネント名</dd>
  <dt>type</dt><dd>チャート種別</dd>
  <dt>:options</dt><dd>オプション</dd>
  <dt>:data</dt><dd>データ</dd>
</dl>

---
# ==========================================
# 📌 SLIDE : 04. CHART TYPE
# ==========================================
layout: cyber-two-cols
---

::header::
## 04. CHART TYPE

::left::

- CoreChart Group
  - <Link to="AreaChart">AreaChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/areachart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="BarChart">BarChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/barchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="BubbleChart">BubbleChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/bubblechart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="CandlestickChart">CandlestickChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/candlestickchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="ColumnChart">ColumnChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/columnchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="ComboChart">ComboChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/combochart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="Histogram">Histogram</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/histogram" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="LineChart">LineChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/linechart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="PieChart">PieChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/piechart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="ScatterChart">ScatterChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/scatterchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
  - <Link to="SteppedAreaChart">SteppedAreaChart</Link>&nbsp;
    <a href="https://developers.google.com/chart/interactive/docs/gallery/steppedareachart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>

::right::
 
- <Link to="AnnotationChart">AnnotationChart</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/annotationchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Calendar">Calendar</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/calendar" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Gantt">Gantt</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/ganttchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Gauge">Gauge</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/gauge" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="GeoChart">GeoChart</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/geochart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Map">Map</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/map" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Orgchart">Orgchart</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/orgchart" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Sankey">Sankey</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/sankey" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Table">Table</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/table" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="Timeline">Timeline</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/timeline" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="TreeMap">TreeMap</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/treemap" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>
- <Link to="WordTree">WordTree</Link>&nbsp;
  <a href="https://developers.google.com/chart/interactive/docs/gallery/wordtree" target="_blank" rel="noopener noreferrer"><carbon-launch /></a>

---
# ==========================================
# 📌 SLIDE : 05. CORECHART - AREACHART
# ==========================================
layout: cyber-two-cols
routeAlias: AreaChart
---

::header::
## 05. CORECHART - AREACHART

::left::

<GoogleCharts 
  type="AreaChart"
  :options="{
    title: 'Company Performance',
    hAxis: {title: 'Year',  titleTextStyle: {color: '#333'}},
    vAxis: {minValue: 0},
    height: 330
  }"
  :data="[
    ['Year', 'Sales', 'Expenses'],
    ['2013',  1000,      400],
    ['2014',  1170,      460],
    ['2015',  660,       1120],
    ['2016',  1030,      540]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 06. CORECHART - BARCHART
# ==========================================
layout: cyber-two-cols
routeAlias: BarChart
---

::header::
## 06. CORECHART - BARCHART

::left::

<GoogleCharts 
  type="BarChart"
  :options="{
          chart: {
            title: 'Company Performance',
            subtitle: 'Sales, Expenses, and Profit: 2014-2017',
          },
          bars: 'horizontal',
          height: 330
  }"
  :data="[
          ['Year', 'Sales', 'Expenses', 'Profit'],
          ['2014', 1000, 400, 200],
          ['2015', 1170, 460, 250],
          ['2016', 660, 1120, 300],
          ['2017', 1030, 540, 350]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 07. CORECHART - BUBBLECHART
# ==========================================
layout: cyber-two-cols
routeAlias: BubbleChart
---

::header::
## 07. CORECHART - BUBBLECHART

::left::

<GoogleCharts 
  type="BubbleChart"
  :options="{
    title: 'Fertility rate vs life expectancy in selected countries (2010).' +
    ' X=Life Expectancy, Y=Fertility, Bubble size=Population, Bubble color=Region',
    hAxis: {title: 'Life Expectancy'},
    vAxis: {title: 'Fertility Rate'},
    bubble: {
      textStyle: {
        auraColor: 'none',
      }
    },
    height: 330
  }"
  :data="[
        ['ID', 'Life Expectancy', 'Fertility Rate', 'Region',     'Population'],
        ['CAN',    80.66,              1.67,      'North America',  33739900],
        ['DEU',    79.84,              1.36,      'Europe',         81902307],
        ['DNK',    78.6,               1.84,      'Europe',         5523095],
        ['EGY',    72.73,              2.78,      'Middle East',    79716203],
        ['GBR',    80.05,              2,         'Europe',         61801570],
        ['IRN',    72.49,              1.7,       'Middle East',    73137148],
        ['IRQ',    68.09,              4.77,      'Middle East',    31090763],
        ['ISR',    81.55,              2.96,      'Middle East',    7485600],
        ['RUS',    68.6,               1.54,      'Europe',         141850000],
        ['USA',    78.09,              2.05,      'North America',  307007000]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 08. CORECHART - CANDLESTICKCHART
# ==========================================
layout: cyber-two-cols
routeAlias: CandlestickChart
---

::header::
## 08. CORECHART - CANDLESTICKCHART

::left::

<GoogleCharts 
  type="CandlestickChart"
  :options="{
      legend:'none',
      height: 330
  }"
  :data="[
      ['Label1', 'Label2', 'Label3', 'Label4', 'Label5'],
      ['Mon', 20, 28, 38, 45],
      ['Tue', 31, 38, 55, 66],
      ['Wed', 50, 55, 77, 80],
      ['Thu', 77, 77, 66, 50],
      ['Fri', 68, 66, 22, 15]
  ]"
/>

::right::

<GoogleCharts 
  type="CandlestickChart"
  :options="{
    legend: 'none',
    bar: { groupWidth: '100%' }, 
    candlestick: {
      fallingColor: { strokeWidth: 0, fill: '#a52714' },
      risingColor: { strokeWidth: 0, fill: '#0f9d58' }
    },
    height: 330
  }"
  :data="[
    ['Label1', 'Label2', 'Label3', 'Label4', 'Label5'],
    ['Mon', 28, 28, 38, 38],
    ['Tue', 38, 38, 55, 55],
    ['Wed', 55, 55, 77, 77],
    ['Thu', 77, 77, 66, 66],
    ['Fri', 66, 66, 22, 22]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 09. CORECHART - COLUMNCHART
# ==========================================
layout: cyber-two-cols
routeAlias: ColumnChart
---

::header::
## 09. CORECHART - COLUMNCHART

::left::

<GoogleCharts 
  type="ColumnChart"
  :options="{
        height: 330,
        legend: { position: 'top', maxLines: 3 },
        bar: { groupWidth: '75%' },
        isStacked: true,
  }"
  :data="[
        ['Genre', 'Fantasy & Sci Fi', 'Romance', 'Mystery/Crime', 'General',
         'Western', 'Literature', { role: 'annotation' } ],
        ['2010', 10, 24, 20, 32, 18, 5, ''],
        ['2020', 16, 22, 23, 30, 16, 9, ''],
        ['2030', 28, 19, 29, 30, 12, 13, '']
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 10. CORECHART - COMBOCHART
# ==========================================
layout: cyber-two-cols
routeAlias: ComboChart
---

::header::
## 10. CORECHART - COMBOCHART

::left::

<GoogleCharts 
  type="ComboChart"
  :options="{
    title : 'Monthly Coffee Production by Country',
    vAxis: {title: 'Cups'},
    hAxis: {title: 'Month'},
    seriesType: 'bars',
    series: {5: {type: 'line'}},
    height: 330
  }"
  :data="[
          ['Month', 'Bolivia', 'Ecuador', 'Madagascar', 'Papua New Guinea', 'Rwanda', 'Average'],
          ['2004/05',  165,      938,         522,             998,           450,      614.6],
          ['2005/06',  135,      1120,        599,             1268,          288,      682],
          ['2006/07',  157,      1167,        587,             807,           397,      623],
          ['2007/08',  139,      1110,        615,             968,           215,      609.4],
          ['2008/09',  136,      691,         629,             1026,          366,      569.6]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 11. CORECHART - HISTOGRAM
# ==========================================
layout: cyber-two-cols
routeAlias: Histogram
---

::header::
## 11. CORECHART - HISTOGRAM

::left::

<GoogleCharts 
  type="Histogram"
  :options="{
    title: 'Charges of subatomic particles',
    legend: { position: 'top', maxLines: 2 },
    colors: ['#5C3292', '#1A8763', '#871B47', '#999999'],
    interpolateNulls: false,
    height: 330
  }"
  :data="[
    ['Quarks', 'Leptons', 'Gauge Bosons', 'Scalar Bosons'],
    [2/3, -1, 0, 0],
    [2/3, -1, 0, null],
    [2/3, -1, 0, null],
    [-1/3, 0, 1, null],
    [-1/3, 0, -1, null],
    [-1/3, 0, null, null],
    [-1/3, 0, null, null]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 12. CORECHART - LINECHART
# ==========================================
layout: cyber-two-cols
routeAlias: LineChart
---

::header::
## 12. CORECHART - LINECHART

::left::

<GoogleCharts 
  type="LineChart"
  :options="{
    title: 'Company Performance',
    curveType: 'function',
    legend: { position: 'bottom' },
    height: 330
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

<GoogleCharts 
  type="LineChart"
  :options="{
    title: 'Company Performance',
    legend: { position: 'bottom' },
    pointSize: 15,
    series: {
      0: { pointShape: 'circle' },
      1: { pointShape: 'diamond', lineDashStyle: [5, 5] },
    },
    height: 330
  }"
  :data="[
    ['Year', 'Sales', 'Expenses'],
    ['2004',  1000,      400],
    ['2005',  1170,      460],
    ['2006',  660,       1120],
    ['2007',  1030,      540]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 13. CORECHART - PIECHART
# ==========================================
layout: cyber-two-cols
routeAlias: PieChart
---

::header::

## 13. CORECHART - PIECHART

::left::

<GoogleCharts 
  type="PieChart"
  :options="{
    title: 'My Daily Activities',
    height: 330,
    is3D: true,
  }"
  :data="[
    ['Task', 'Hours per Day'],
    ['Work',     11],
    ['Commute',  4],
    ['Sleep',    9]
  ]"
/>

::right::

<style>
text {
  filter: drop-shadow(2px 2px 2px rgba(0, 0, 0, 0.6)) !important;
}
</style>

<GoogleCharts 
  type="PieChart"
  :options="{
    title: '1日の時間配分',
    pieHole: 0.4,
    slices: {
      0: { offset: 0.2 },
      1: { offset: 0.0 },
      2: { offset: 0.0 },
      3: { offset: 0.0 },
      4: { offset: 0.0 },
    },
    legend: 'none', 
    pieSliceText: 'label', 
    pieSliceTextStyle: {
      color: '#ffffff',
      fontSize: 14,
      bold: true
    },
    height: 330
  }"
  :data="[
    ['Task', 'Hours per Day'],
    ['仕事',  8],
    ['食事',  2],
    ['通勤',  2],
    ['趣味',  4],
    ['睡眠',  8]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 14. CORECHART - SCATTERCHART
# ==========================================
layout: cyber-two-cols
routeAlias: ScatterChart
---

::header::
## 14. CORECHART - SCATTERCHART

::left::

<GoogleCharts 
  type="ScatterChart"
  :options="{
    title: 'Age vs. Weight comparison',
    hAxis: {title: 'Age', minValue: 0, maxValue: 15},
    vAxis: {title: 'Weight', minValue: 0, maxValue: 15},
    legend: 'none',
    height: 330
  }"
  :data="[
    ['Age', 'Weight'],
    [ 8,      12],
    [ 4,      5.5],
    [ 11,     14],
    [ 4,      5],
    [ 3,      3.5],
    [ 6.5,    7]
  ]"
/>

::right::

<GoogleCharts 
  type="ScatterChart"
  :options="{
    hAxis: { 
      title: 'Completeness of Vision →', 
      minValue: -100, 
      maxValue: 100,
      textPosition: 'none'
    },
    vAxis: {
      title: 'Ability to Execute →', 
      minValue: -100, 
      maxValue: 100,
      textPosition: 'none'
    },
    legend: 'none',
    pointSize: 10,
    pointShape: 'circle',
    colors: ['#1a73e8'],
    annotations: {
      textStyle: { fontSize: 12, color: '#000' },
      alwaysOnTop: true,
      stem: {
        color: '#FFFFFF',
        length: 5
      }
    },
    height: 330
  }"
  :data="[
    ['X', 'Y1', {role: 'annotation'}],
    [  50,  70, '　　　　　　Company A'],
    [ -60,  15, '　　　　　　Company B'],
    [- 30, -40, '　　　　　　Company C'],
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 15. CORECHART - STEPPEDAREACHART
# ==========================================
layout: cyber-two-cols
routeAlias: SteppedAreaChart
---

::header::
## 15. CORECHART - STEPPEDAREACHART

::left::


<GoogleCharts 
  type="SteppedAreaChart"
  :options="{
          isStacked: true,
          height: 330,
          legend: {position: 'top', maxLines: 3},
          vAxis: {minValue: 0}
  }"
  :data="[
          ['Director (Year)',  'Rotten Tomatoes', 'IMDB'],
          ['Alfred Hitchcock (1935)', 8.4,         7.9],
          ['Ralph Thomas (1959)',     6.9,         6.5],
          ['Don Sharp (1978)',        6.5,         6.4],
          ['James Hawes (2008)',      4.4,         6.2]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 16. ANNOTATIONCHART
# ==========================================
layout: cyber-two-cols
routeAlias: AnnotationChart
---

::header::
## 16. ANNOTATIONCHART

::left::

<GoogleCharts 
  type="AnnotationChart"
  :options="{
    displayAnnotations: true,
    height: 330
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
# 📌 SLIDE : 17. CALENDAR
# ==========================================
layout: cyber-two-cols
routeAlias: Calendar
---

::header::
## 17. CALENDAR

::left::

<GoogleCharts 
  type="Calendar"
  :options="{
    title: 'Red Sox Attendance',
    height: 330
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

::right::

---
# ==========================================
# 📌 SLIDE : 18. GANTT
# ==========================================
layout: cyber-two-cols
routeAlias: Gantt
---

::header::
## 18. GANTT

::left::

<GoogleCharts 
  type="Gantt"
  language="us"
  :options="{
    height: 330
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
# 📌 SLIDE : 19. GAUGE
# ==========================================
layout: cyber-two-cols
routeAlias: Gauge
---

::header::
## 19. GAUGE

::left::

<GoogleCharts 
  type="Gauge"
  :options="{
    height: 330
  }"
  :data="[
    ['Label', 'Value'],
    ['CPU', 85]
  ]"
/>

::right::

---
# ==========================================
# 📌 SLIDE : 20. GEOCHART
# ==========================================
layout: cyber-two-cols
routeAlias: GeoChart
---

::header::
## 20. GEOCHART

::left::

<GoogleCharts 
  type="GeoChart"
  :options="{
    height: 330,
    region: 'JP',
    resolution: 'provinces',
  }"
  :data="[
    ['都道府県', '値'],
    ['北海道', 100]
  ]"
/>

::right::

<GoogleCharts 
  type="GeoChart"
  :options="{
    height: 330,
  }"
  :data="[
          ['Country', 'Popularity'],
          ['Germany', 200],
          ['United States', 300],
          ['Brazil', 400],
          ['Canada', 500],
          ['France', 600],
          ['RU', 700]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 21. MAP
# ==========================================
layout: cyber-two-cols
routeAlias: Map
ribbon: WIP
---

::header::
## 21. MAP

::left::
<!--
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
-->

::right::

<p class="alert">Need a mapsApiKey </p>

---
# ==========================================
# 📌 SLIDE : 22. ORGCHART
# ==========================================
layout: cyber-two-cols
routeAlias: OrgChart
---

::header::
## 22. ORGCHART

::left::

<GoogleCharts 
  type="OrgChart"
  :options="{
    height: 330
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
# 📌 SLIDE : 23. SANKEY
# ==========================================
layout: cyber-two-cols
routeAlias: Sankey
---

::header::
## 23. SANKEY

::left::

<GoogleCharts 
  type="Sankey"
  :options="{
    height: 330
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

<GoogleCharts 
  type="Sankey"
  :options="{
    height: 330
  }"
  :data="[
    [ 'From', 'To', 'Weight' ],
    [ 'Brazil', 'Portugal', 5 ],
    [ 'Brazil', 'France', 1 ],
    [ 'Brazil', 'Spain', 1 ],
    [ 'Brazil', 'England', 1 ],
    [ 'Canada', 'Portugal', 1 ],
    [ 'Canada', 'France', 5 ],
    [ 'Canada', 'England', 1 ],
    [ 'Mexico', 'Portugal', 1 ],
    [ 'Mexico', 'France', 1 ],
    [ 'Mexico', 'Spain', 5 ],
    [ 'Mexico', 'England', 1 ],
    [ 'USA', 'Portugal', 1 ],
    [ 'USA', 'France', 1 ],
    [ 'USA', 'Spain', 1 ],
    [ 'USA', 'England', 5 ],
    [ 'Portugal', 'Angola', 2 ],
    [ 'Portugal', 'Senegal', 1 ],
    [ 'Portugal', 'Morocco', 1 ],
    [ 'Portugal', 'South Africa', 3 ],
    [ 'France', 'Angola', 1 ],
    [ 'France', 'Senegal', 3 ],
    [ 'France', 'Mali', 3 ],
    [ 'France', 'Morocco', 3 ],
    [ 'France', 'South Africa', 1 ],
    [ 'Spain', 'Senegal', 1 ],
    [ 'Spain', 'Morocco', 3 ],
    [ 'Spain', 'South Africa', 1 ],
    [ 'England', 'Angola', 1 ],
    [ 'England', 'Senegal', 1 ],
    [ 'England', 'Morocco', 2 ],
    [ 'England', 'South Africa', 7 ],
    [ 'South Africa', 'China', 5 ],
    [ 'South Africa', 'India', 1 ],
    [ 'South Africa', 'Japan', 3 ],
    [ 'Angola', 'China', 5 ],
    [ 'Angola', 'India', 1 ],
    [ 'Angola', 'Japan', 3 ],
    [ 'Senegal', 'China', 5 ],
    [ 'Senegal', 'India', 1 ],
    [ 'Senegal', 'Japan', 3 ],
    [ 'Mali', 'China', 5 ],
    [ 'Mali', 'India', 1 ],
    [ 'Mali', 'Japan', 3 ],
    [ 'Morocco', 'China', 5 ],
    [ 'Morocco', 'India', 1 ],
    [ 'Morocco', 'Japan', 3 ]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 24. TABLE
# ==========================================
layout: cyber-two-cols
routeAlias: Table
---

::header::
## 24. TABLE

::left::

<GoogleCharts 
  type="Table"
  :options="{
    title: 'My Daily Activities',
    showRowNumber: true,
    width: '100%',
  }"
  :data="[
    ['Name',  'Salary', 'Full Time Employee'],
    ['Mike',  {v: 10000, f: '$10,000'}, true],
    ['Jim',   {v:8000,   f: '$8,000'},  false],
    ['Alice', {v: 12500, f: '$12,500'}, true],
  ]"
/>

::right::

<GoogleCharts 
  type="Table"
  :options="{
    title: 'WoW Midnight DPS Tier List',
    allowHtml: true, 
    sort: 'disable',
    showRowNumber: false,
    width: '100%',
  }"
  :data="[
    [
      '<div class=\'tier-splus\'>　　S+　　</div>', 
      `<div class=\'icon-container\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/warrior_arms.png?raw=true\' title=\'Arms Warrior\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/mage_arcane.png?raw=true\' title=\'Arcane Mage\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/dk_unholy.png?raw=true\' title=\'Unholy Death Knight\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/shaman_elem.png?raw=true\' title=\'Elemental Shaman\'>
      </div>`
    ],
    [
      '<div class=\'tier-s\'>S</div>', 
      `<div class=\'icon-container\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/warrior_fury.png?raw=true\' title=\'Fury Warrior\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/mage_fire.png?raw=true\' style=\'width: 13%; display: inline\' title=\'Fire Mage\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/warlock_demono.png?raw=true\' title=\'Demonology Warlock\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/druid_balance.png?raw=true\' title=\'Balance Druid\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/dh_havoc.png?raw=true\' title=\'Havoc Demon Hunter\'>
      </div>`
    ],
    [
      '<div class=\'tier-a\'>A</div>', 
      `<div class=\'icon-container\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/mage_frost.png?raw=true\' title=\'Frost Mage\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/dk_frost.png?raw=true\' title=\'Frost Death Knight\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/shaman_enhancement.png?raw=true\' title=\'Enhancement Shaman\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/warlock_destru.png?raw=true\' title=\'Destruction Warlock\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/rogue_sub.png?raw=true\' title=\'Subtlety Rogue\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/rogue_assa.png?raw=true\' title=\'Assassination Rogue\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/hunter_mm.png?raw=true\' title=\'Marksmanship Hunter\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/hunter_bm.png?raw=true\' title=\'Beast Mastery Hunter\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/paladin_ret.png?raw=true\' title=\'Retribution Paladin\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/monk_ww.png?raw=true\' title=\'Windwalker Monk\'>
        <img src=\'https://warcraft.wiki.gg/images/Classicon_demonhunter_void.png?673e44\' title=\'Devourer Demon Hunter\'>
      </div>`
    ],
    [
      '<div class=\'tier-b\'>B</div>', 
      `<div class=\'icon-container\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/warlock_affli.png?raw=true\' title=\'Affliction Warlock\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/druid_feral.png?raw=true\' title=\'Feral Druid\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/rogue_outlaw.png?raw=true\' title=\'Outlaw Rogue\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/hunter_survival.png?raw=true\' title=\'Survival Hunter\'>
        <img src=\'https://github.com/danetch/wowspecsemojis/blob/master/priest_shadow.png?raw=true\' title=\'Shadow Priest\'>
        <img src=\'https://warcraft.wiki.gg/images/Classicon_evoker_devastation.png?b0028b\' title=\'Devastation Evoker\'>
        <img src=\'https://warcraft.wiki.gg/images/Classicon_evoker_augmentation.png?cccbac\' title=\'Augmentation Evoker\'>
      </div>`
    ]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 25. TIMELINE
# ==========================================
layout: cyber-two-cols
routeAlias: Timeline
---

::header::
## 25. TIMELINE

::left::

<GoogleCharts 
  type="Timeline"
  :options="{
    width: '100%',
    height: 175
  }"
  :data="[
    [ 'President', 'Start', 'End' ],
    [ 'Washington', new Date(1789, 3, 30), new Date(1797, 2, 4) ],
    [ 'Adams',      new Date(1797, 2, 4),  new Date(1801, 2, 4) ],
    [ 'Jefferson',  new Date(1801, 2, 4),  new Date(1809, 2, 4) ]
  ]"
/>

<GoogleCharts 
  type="Timeline"
  :options="{
    width: '100%',
    height: 175
  }"
  :data="[
    [ 'Position', 'Name', 'Start', 'End' ],
    [ 'President', 'George Washington', new Date(1789, 3, 30), new Date(1797, 2, 4) ],
    [ 'President', 'John Adams', new Date(1797, 2, 4), new Date(1801, 2, 4) ],
    [ 'President', 'Thomas Jefferson', new Date(1801, 2, 4), new Date(1809, 2, 4) ],
    [ 'Vice President', 'John Adams', new Date(1789, 3, 21), new Date(1797, 2, 4)],
    [ 'Vice President', 'Thomas Jefferson', new Date(1797, 2, 4), new Date(1801, 2, 4)],
    [ 'Vice President', 'Aaron Burr', new Date(1801, 2, 4), new Date(1805, 2, 4)],
    [ 'Vice President', 'George Clinton', new Date(1805, 2, 4), new Date(1812, 3, 20)],
    [ 'Secretary of State', 'John Jay', new Date(1789, 8, 25), new Date(1790, 2, 22)],
    [ 'Secretary of State', 'Thomas Jefferson', new Date(1790, 2, 22), new Date(1793, 11, 31)],
    [ 'Secretary of State', 'Edmund Randolph', new Date(1794, 0, 2), new Date(1795, 7, 20)],
    [ 'Secretary of State', 'Timothy Pickering', new Date(1795, 7, 20), new Date(1800, 4, 12)],
    [ 'Secretary of State', 'Charles Lee', new Date(1800, 4, 13), new Date(1800, 5, 5)],
    [ 'Secretary of State', 'John Marshall', new Date(1800, 5, 13), new Date(1801, 2, 4)],
    [ 'Secretary of State', 'Levi Lincoln', new Date(1801, 2, 5), new Date(1801, 4, 1)],
    [ 'Secretary of State', 'James Madison', new Date(1801, 4, 2), new Date(1809, 2, 3)]
  ]"
/>

::right::

<GoogleCharts 
  type="Timeline"
  :options="{
    timeline: {
      showRowLabels: true
    },
    hAxis: {
      format: 'HH:mm',
    },
    height: 214
  }"
  :data="[
    [ 'Position', 'Name', 'Start', 'End' ],
    [ 'PDT',    'Elusive Moonfish', new Date(0, 0, 0, 0, 0, 0), new Date(0, 0, 0, 6, 0, 0) ],
    [ 'PDT',    'Golden Sunsoaker', new Date(0, 0, 0, 6, 0, 0), new Date(0, 0, 0, 18, 0, 0) ],
    [ 'PDT',    'Elusive Moonfish', new Date(0, 0, 0, 18, 0, 0), new Date(0, 0, 0, 24, 0, 0) ],
    [ 'JST',  'Golden Sunsoaker', new Date(0, 0, 0, 0, 0, 0), new Date(0, 0, 0, 10, 0, 0) ],
    [ 'JST',  'Elusive Moonfish', new Date(0, 0, 0, 10, 0, 0), new Date(0, 0, 0, 22, 0, 0) ],
    [ 'JST',  'Golden Sunsoaker', new Date(0, 0, 0, 22, 0, 0), new Date(0, 0, 0, 24, 0, 0) ],
    [ '実績1',   'Golden Sunsoaker', new Date(0, 0, 0, 7, 17, 54), new Date(0, 0, 0, 7, 17, 55) ],
    [ '実績1',   'Golden Sunsoaker', new Date(0, 0, 0, 7, 22, 27), new Date(0, 0, 0,  7, 22, 28) ],
    [ '実績1',   'Golden Sunsoaker', new Date(0, 0, 0, 22, 48, 56), new Date(0, 0, 0, 22, 48, 57) ],
    [ '実績2',   'Elusive Moonfish', new Date(0, 0, 0, 12, 22, 3), new Date(0, 0, 0, 12, 22, 4) ],
  ]"
/>

<GoogleCharts 
  type="Timeline"
  :options="{
    timeline: {
      showRowLabels: true
    },
    hAxis: {
      format: 'HH:mm',
    },
    height: 132
  }"
  :data="[
    [ 'Position', 'Name', 'Start', 'End' ],
    [ 'PST',    'Elusive Moonfish', new Date(0, 0, 0, 0, 0, 0), new Date(0, 0, 0, 6, 0, 0) ],
    [ 'PST',    'Golden Sunsoaker', new Date(0, 0, 0, 6, 0, 0), new Date(0, 0, 0, 18, 0, 0) ],
    [ 'PST',    'Elusive Moonfish', new Date(0, 0, 0, 18, 0, 0), new Date(0, 0, 0, 24, 0, 0) ],
    [ 'JST',  'Golden Sunsoaker', new Date(0, 0, 0, 0, 0, 0), new Date(0, 0, 0, 11, 0, 0) ],
    [ 'JST',  'Elusive Moonfish', new Date(0, 0, 0, 11, 0, 0), new Date(0, 0, 0, 23, 0, 0) ],
    [ 'JST',  'Golden Sunsoaker', new Date(0, 0, 0, 23, 0, 0), new Date(0, 0, 0, 24, 0, 0) ],
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 26. TREEMAP
# ==========================================
layout: cyber-two-cols
routeAlias: TreeMap
---

::header::
## 26. TREEMAP

::left::

<GoogleCharts 
  type="TreeMap"
  :options="{
    height: 330,
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
# 📌 SLIDE : 27. WORDTREE
# ==========================================
layout: cyber-two-cols
routeAlias: WordTree
---

::header::
## 27. WORDTREE

::left::

<GoogleCharts 
  type="WordTree"
  :options="{
    height: 330,
    wordtree: {
      format: 'implicit',
      word: 'cats',
      width: 500
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
# 📌 SLIDE : 28. Known Issues
# ==========================================
layout: cyber-one-col
---

::header::
## 28. Known Issues

::default::

<dl>
<dt>🔥 不具合(調査中)</dt>
<dd>
<br><br>
</dd>
<dt>✅ 不具合(リリース待ち)</dt>
<dd>
<br><br>
</dd>
<dt>🚫 制限事項</dt>
<dd>
- Map表示にAPIキーが必要<br>
- GeoChartのmarkersで都市名から緯度・経度を解決する場合にAPIキーが必要
</dd>
<dt>⏳ 保留</dt>
<dd>
- VegaChart
</dd>
</dl>

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
# 📌 SLIDE : 101. PROFILE
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 101. PROFILE

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
# 📌 SLIDE : 102. Slide Flow Template
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 102. Slide Flow Template

::default::

<dl>
  <dt>1. 背景・課題（Why）</dt>
  <dd>
  - 現行システムや業務が抱えていた問題点<br>
  - なぜ既存の方法ではダメなのか
  </dd>
  <dt>2. 解決策の提示（What）</dt>
  <dd>
  - 導入・採用した技術やアーキテクチャの概要<br>
  - その技術を選んだ決め手（技術選定の理由）
  </dd>
  <dt>3. 技術的詳細・工夫点（How）</dt>
  <dd>
  - システム構成図（アーキテクチャ図）<br>
  - 実装上のこだわりや、直面した壁とそれをどう乗り越えたか<br>
  - コードスニペット（必要に応じて数行〜1画面に収まる量で）
  </dd>
  <dt>4. 成果・効果（Result）</dt>
  <dd>
  - 導入後の定量的効果（例：レスポンス速度が◯%向上、運用コスト◯%削減）<br>
  - 定性的効果（例：開発メンバーの体験向上、運用の心理的負荷軽減）
  </dd>
  <dt>5. 今後の展望（Next）</dt>
  <dd>
  - 今後解決すべき残された課題や、次のフェーズでやりたいこと
  </dd>
</dl>

---
# ==========================================
# 📌 SLIDE : 103. FRONT MATTER
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 103. FRONT MATTER

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
# 📌 SLIDE : 104. LAYOUTS
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 104. LAYOUTS

::default::

| LAYOUT NAME | PURPOSE | PARTITION |
| :--- | :--- | :--- |
| `cyber-cover` | Cover | - `::command::` <br> - `::default::` <br> - `::subtitle::` |
| `cyber-one-col` | One Column | - `::header::` <br> - `::default::` |
| `cyber-two-cols` | Two Columns | - `::header::` <br> - `::left::` <br> - `::right::`|
| `lain-end` | Closing Slide | (none) |

---
# ==========================================
# 📌 SLIDE : 105. CYBER TABLE
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 105. TABLE

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
# 📌 SLIDE : 106. CODEBLOCK
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 106. CODEBLOCK

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
# 📌 SLIDE : 107. LIST
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 107. LIST

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
# 📌 SLIDE : 108. CORNER RIBBON / FOOTER
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 108. CORNER RIBBON / FOOTER

::left::

CORNER RIBBON - TEMPLATE

```yaml
---
ribbon: TEMPLATE
---
```

CORNER RIBBON - WIP

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
# 📌 SLIDE : 109. DECORATION
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 109. DECORATION

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
# 📌 SLIDE : 110. EMBED
# ==========================================
layout: cyber-two-cols
ribbon: TEMPLATE
---

::header::
## 110. EMBED

::left::

<Youtube id="I47iGCfH7EI" width="100%" height="330px" />

::right::

<Youtube id="eKnR3qyjbVQ" width="100%" height="330px" />

---
# ==========================================
# 🔖 CLOSING : END
# ==========================================
layout: lain-end
ribbon: TEMPLATE
---
