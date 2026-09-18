<template>
  <div class="slidev-addon-google-charts-wrapper" :style="{ width: width, height: height }">
    <GChart
      v-if="isReady"
      :type="type"
      :data="data"
      :options="options"
      :settings="{ packages: chartPackages, language: 'ja' }"
    />
    <!-- 読み込み中のプレースホルダー（必要であれば） -->
    <div v-else class="loading-placeholder">
      Loading chart...
    </div>
  </div>
</template>

<script setup>
import { computed, nextTick, ref } from 'vue'
import { GChart } from 'vue-google-charts'
// 💡 Slidevの現在のページ状態を監視するための関数をインポート
import { onSlideEnter, onSlideLeave } from '@slidev/client'

const props = defineProps({
  type: { type: String, required: true },
  data: { type: Array, required: true },
  options: { type: Object, default: () => ({}) },
  width: { type: String, default: '100%' },
  height: { type: String, default: '300px' }
})

const chartPackages = computed(() => {
  const typeLower = props.type.toLowerCase()
  if (typeLower === 'annotationchart') return ['annotationchart']
  if (typeLower === 'bar') return ['bar']
  if (typeLower === 'calendar') return ['calendar']
  if (typeLower === 'charteditor') return ['charteditor']
  if (typeLower === 'controls') return ['controls']
  if (typeLower === 'gantt') return ['gantt']
  if (typeLower === 'gauge') return ['gauge']
  if (typeLower === 'geochart') return ['geochart']
  if (typeLower === 'line') return ['line']
  if (typeLower === 'map') return ['map']
  if (typeLower === 'motionchart') return ['motionchart']
  if (typeLower === 'orgchart') return ['orgchart']
  if (typeLower === 'sankey') return ['sankey']
  if (typeLower === 'table') return ['table']
  if (typeLower === 'timeline') return ['timeline']
  if (typeLower === 'treemap') return ['treemap']
  if (typeLower === 'wordtree') return ['wordtree']
  return ['corechart']
})

const isReady = ref(false)

// 💡 このスライドに画面が切り替わってきた瞬間に実行される
onSlideEnter(async () => {
  // 1. スライドが切り替わり、DOMサイズ（幅・高さ）が確定するのを待つ
  await nextTick()
  // 2. フォントの準備ができるのを待つ
  await document.fonts.ready
  
  // 3. スライドのアニメーション（約100〜200ms）をやり過ごしてから安全に描画
  setTimeout(() => {
    isReady.value = true
  }, 250)
})

// 💡 ユーザーが他のスライドに移動した瞬間に実行される
onSlideLeave(() => {
  // 一旦グラフの描画をリセット（次回戻ってきた時に再計算させるため）
  isReady.value = false
})
</script>

<style scoped>
/*
.slidev-addon-google-charts-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1rem 0;
}
 */

/* グラフが表示される前のカクつきを防ぐため、親要素に高さを確保しておくと綺麗です */
/*
.slidev-addon-google-charts-wrapper {
  min-height: 400px; 
  display: flex;
  align-items: center;
  justify-content: center;
}
*/
.loading-placeholder {
  color: #888;
}

/* ==========================================================================
   Google Chart OrgChart - Modern Flat Theme
   ========================================================================== */

   /* テーブル全体の文字色と背景色を上書き（ここは維持） */

.slidev-addon-google-charts-wrapper :deep(.google-visualization-orgchart-node) {
  color: #333333 !important;
  background-color: #ffffff !important;
}

.slidev-addon-google-charts-wrapper :deep(.google-visualization-orgchart-node-medium) {
  color: #333333 !important;
  background-color: #ffffff !important;
}

/* ==========================================================================
   Google Chart Table - Modern Flat Theme
   ========================================================================== */

   /* テーブル全体の文字色と背景色を上書き（ここは維持） */
.slidev-addon-google-charts-wrapper :deep(.google-visualization-table-table) {
  color: #333333 !important;
  background-color: #ffffff !important;
}

.slidev-addon-google-charts-wrapper :deep(.google-visualization-table-td) {
  color: #333333 !important;
  background-color: #ffffff !important;
}

/* ヘッダー：余計な余白や境界線の変更をせず、グラデーションだけを消す */
.slidev-addon-google-charts-wrapper :deep(.google-visualization-table-th) {
  background-image: none !important;     /* 👈 古くさいグラデーションを消去 */
  background-color: #2c3e50 !important;  /* 👈 フラットな背景色にする */
  color: #ffffff !important;             /* 👈 文字を白にする */
}

/* ヘッダーのホバー時もグラデーションを消す */
.slidev-addon-google-charts-wrapper :deep(.google-visualization-table-th:hover) {
  background-image: none !important;
  background-color: #34495e !important;
}

/* ==========================================================================
   Google Chart Table - Tier List
   ========================================================================== */

/* color
  rank
    S+  #ff7f7f
    S   #ffbf7f
    A   #ffdf7f
    B   #ffff7f
    C   #bfff7f
    D   #7fff7f
  right #333
  border  #000
*/

.slidev-addon-google-charts-wrapper :deep(.icon-container) {
  background: #333;
}

.slidev-addon-google-charts-wrapper :deep(th:has(:is(.icon-container, .tier-splus))) {
  margin: 0 !important;
  padding: 0 !important;
  height: 1px;
  border-color: black !important;
}

.slidev-addon-google-charts-wrapper :deep(td:has(:is(.icon-container, .tier-s, .tier-a, .tier-b))) {
  margin: 0 !important;
  padding: 0 !important;
  height: 1px;
  border-color: black !important;
}

.slidev-addon-google-charts-wrapper :deep(img.tierlist) {
  display: inline !important;
  width: 15% !important;
}

/* S+ */
.slidev-addon-google-charts-wrapper :deep(.tier-splus) {
  background-color: #ff7f7f !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
  color: black;
}

/* S */
.slidev-addon-google-charts-wrapper :deep(.tier-s) {
  background-color: #ffbf7f !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* A */
.slidev-addon-google-charts-wrapper :deep(.tier-a) {
  background-color: #ffdf7f !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* B */
.slidev-addon-google-charts-wrapper :deep(.tier-b) {
  background-color: #ffff7f !important;
  text-align: center !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* C */
.slidev-addon-google-charts-wrapper :deep(.tier-c) {
  background-color: #bfff7f !important;
  text-align: center !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* D */
.slidev-addon-google-charts-wrapper :deep(.tier-d) {
  background-color: #7fff7f !important;
  text-align: center !important;
  width: 100% !important;
  height: 100% !important;
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
