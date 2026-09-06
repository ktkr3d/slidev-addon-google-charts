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

const chartPackages = computed(() => {
  const typeLower = props.type.toLowerCase()
  if (typeLower === 'annotationchart') return ['annotationchart']
  if (typeLower === 'bar') return ['bar']
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
</script>

<style scoped>
.slidev-google-chart-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1rem 0;
}
</style>
