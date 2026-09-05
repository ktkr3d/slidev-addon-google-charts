<template>
  <div class="slidev-google-chart-wrapper" :style="{ width: width, height: height }">
    <GChart
      :type="type"
      :data="data"
      :options="options"
      :settings="{ packages: chartPackages, language: 'ja' }"
    />
  </div>
</template>

<script setup>
import { computed } from 'vue'
import { GChart } from 'vue-google-charts'

const props = defineProps({
  type: { type: String, required: true },
  data: { type: Array, required: true },
  options: { type: Object, default: () => ({}) },
  width: { type: String, default: '100%' },
  height: { type: String, default: '400px' }
})

// 指定されたすべてのパッケージを網羅するように修正
const chartPackages = computed(() => {
  const typeLower = props.type.toLowerCase()
  if (typeLower === 'timeline') return ['timeline']
  if (typeLower === 'gantt') return ['gantt']
  if (typeLower === 'orgchart') return ['orgchart']
  if (typeLower === 'gauge') return ['gauge']
  if (typeLower === 'treemap') return ['treemap']
  if (typeLower === 'wordtree') return ['wordtree']
  if (typeLower === 'geochart') return ['geochart'] // 🟢 追加
  if (typeLower === 'sankey') return ['sankey']     // 🟢 追加
  return ['corechart'] // LineChart, BarChart, PieChartなどはここに含まれます
})
</script>

<style scoped>
.slidev-google-chart-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1rem 0;
}
</style>
