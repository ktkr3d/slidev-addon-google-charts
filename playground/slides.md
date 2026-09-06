---
# ==========================================
# 🔖 THEME : テーマ
# ==========================================
theme: default
background: ''
class: text-center
lineNumbers: true
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
# 📌 SLIDE : 02. CHART TYPE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 02. CHART TYPE

::left::

- [ ] **annotationchart** - 注釈付きタイムライン
- [ ] **bar** - マテリアルデザイン棒グラフ
- [ ] **charteditor** - チャートエディタ
- [ ] **controls** - ダッシュボードコントロール
- [X] **corechart** - 折れ線・棒・円など基本グラフ
- [ ] **gantt** - ガントチャート
- [X] **gauge** - メーター・ゲージ
- [X] **geochart** - 国や地域のデータマップ
- [ ] **line** - マテリアルデザイン折れ線グラフ

::right::
 
- [ ] **map** - Google マップ地図表示
- [ ] **motionchart** - モーションチャート
- [ ] **orgchart** - 組織図
- [ ] **sankey** - サンキー・ダイアグラム
- [X] **table** - データ表
- [ ] **timeline** - スケジュールタイムライン
- [ ] **treemap** - ツリーマップ
- [ ] **wordtree** - テキストワードツリー

チェック付きはレイアウト例を掲載しています。

---
# ==========================================
# 📌 SLIDE : 03. SETUP
# ==========================================
layout: cyber-two-cols
---

::header::
## 03. SETUP

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
# 📌 SLIDE : 04. HOW TO USE
# ==========================================
layout: cyber-two-cols
---

::header::
## 04. HOW TO USE

::left::

```vue
<GoogleCharts 
  type="GeoChart"
  width="200%"
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
  <li><strong>width</strong> — 幅（デフォルト: 100%）</li>
  <li><strong>height</strong> — 高さ（デフォルト: 400px）</li>
  <li><strong>:options</strong> — オプション</li>
  <li><strong>:data</strong> — データ</li>
</ul>

---
# ==========================================
# 📌 SLIDE : 05. GOOGLE CHARTS - CORECHART
# ==========================================
layout: cyber-two-cols
---

::header::
## 05. GOOGLE CHARTS - CORECHART

::left::

CoreChart / PieChart 円グラフ

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

<br><br><br>

<GoogleCharts 
  type="PieChart"
  height="100px"
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
# 📌 SLIDE : 06. GOOGLE CHARTS - GAUGE
# ==========================================
layout: cyber-two-cols
---

::header::
## 06. GOOGLE CHARTS - GAUGE

::left::

Gauge メーター・ゲージ

```vue
<GoogleCharts 
  type="Gauge"
  height="200px"
  :data="[
    ['Label', 'Value'],
    ['CPU', 85]
  ]"
/>
```

::right::

<br>

<GoogleCharts 
  type="Gauge"
  height="200px"
  :data="[
    ['Label', 'Value'],
    ['CPU', 85]
  ]"
/>

---
# ==========================================
# 📌 SLIDE : 07. GOOGLE CHARTS - GEOCHART
# ==========================================
layout: cyber-two-cols
---

::header::
## 07. GOOGLE CHARTS - GEOCHART

::left::

GeoChart 国や地域のデータマップ

```vue
<GoogleCharts 
  type="GeoChart"
  height="200px"
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

<br><br><br>

<GoogleCharts 
  type="GeoChart"
  width="130%"
  height="200px"
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
# 📌 SLIDE : 08. GOOGLE CHARTS - TABLE
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 08. GOOGLE CHARTS - TABLE

::left::

Table データ表

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
  height="200px"
  :options="{
    title: 'My Daily Activities'
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
# 📌 SLIDE : 09. GOOGLE CHARTS - (REST)
# ==========================================
layout: cyber-two-cols
ribbon: WIP
---

::header::
## 09. GOOGLE CHARTS - (UNTESTED)

::left::

- annotationchart 注釈付きタイムライン
- bar マテリアルデザイン棒グラフ
- charteditor チャートエディタ
- controls ダッシュボードコントロール
- gantt ガントチャート
- line マテリアルデザイン折れ線グラフ
- map Google マップ地図表示

::right::

- motionchart モーションチャート
- orgchart 組織図
- sankey サンキー・ダイアグラム
- timeline スケジュールタイムライン
- treemap ツリーマップ
- wordtree テキストワードツリー

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
## 92. CYBER LAYOUTS

::default::

| LAYOUT NAME | PURPOSE | PARTITION |
| :--- | :--- | :--- |
| `cyber-cover` | 表紙 | - `::command::` <br> - `::default::` <br> - `::subtitle::` |
| `cyber-one-col` | スライド(1カラム) | - `::header::` <br> - `::default::` |
| `cyber-two-cols` | スライド(2カラム) | - `::header::` <br> - `::left::` <br> - `::right::`|
| `lain-end` | クロージング | (なし) |

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

表紙

```yaml
theme: default
background: ''
class: text-center
lineNumbers: true
drawings:
  persist: false
title: Arch Linux Style Presentation
addons:
  - slidev-addon-google-charts
layout: cyber-cover
highlighter: shiki
transition: fade
```

::right::

スライド(1カラム)

```yaml
layout: cyber-one-col
```

スライド(2カラム)

```yaml
layout: cyber-one-col
```

クロージング

```yaml
layout: cyber-one-col
```

---
# ==========================================
# 📌 SLIDE : 94. CYBER TABLE
# ==========================================
layout: cyber-one-col
ribbon: TEMPLATE
---

::header::
## 94. CYBER TABLE

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
```bash
# Arch Linux パッケージマネージャー
sudo pacman -Syu
sudo pacman -S neovim tmux zsh

# 特徴的なパッケージの導入
yay -S slidev-cli-git
```

::right::
<ul class="cyber-list text-lg">
  <li><strong>Pacman Optimization</strong> — ミラーリストを最速に同期。</li>
  <li><strong>Development Tools</strong> — 開発に必要なミニマル環境をワンコマンドで構築。</li>
  <li><strong>Bleeding Edge</strong> — 常に最新のソフトウェアをローリングリリース。</li>
</ul>

<!--
<div class="mt-6 border border-coolgray-800 rounded p-1 bg-black/40">
  <img src="https://unsplash.com" class="w-full opacity-80 filter saturate-50 rounded" alt="Cyberpunk Code">
</div>
-->

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

```text
- [X] Closed
- [ ] Open
```

::right::

- [X] Closed
- [ ] Open

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

RIBBON / TEMPLATE

```yaml
---
ribbon: TEMPLATE
---
```

RIBBON / WIP

```yaml
---
ribbon: WIP
---
```

::right::

FOOTER / Default

```text
```
> LAYER_SLIDETITLE

FOOTER / Custom

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

- <p class="point">Point</p>

```html
<p class="point">Point</p>
```

- <p class="alert">Alert</p>

```html
<p class="alert">Alert</p>
```

::right::

---
# ==========================================
# 🔖 CLOSING : END
# ==========================================
layout: lain-end
ribbon: TEMPLATE
---
