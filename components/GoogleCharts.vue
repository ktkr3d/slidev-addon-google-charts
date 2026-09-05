<!-- components/GoogleCharts.vue -->
<script setup lang="ts">
import { GChart } from 'vue-google-charts';

defineProps<{
  type: string
  data: any[]
  options?: object
}>()

const chartSettings = {
  packages: [
    'corechart',
    'geochart',
    'gauge',
    'gantt',
    'sankey',
    'timeline',
    'treemap',
    'wordtree',
    'orgchart'
  ]
}

const defaultOptions = {
  width: '100%',
  height: '350px',
  backgroundColor: 'transparent',
  chartArea: { width: '80%', height: '80%' }
}
</script>

<template>
    <div class="my-google-chart">
        <GChart :type="type" :data="data" :options="{ ...defaultOptions, ...options }" :settings="chartSettings" />
    </div>
</template>

<style scoped>
.my-google-chart {
    width: 100%;
    display: flex;
    justify-content: center;
}
</style>
