<!-- 📄 global-bottom.vue -->
<script setup lang="ts">
import { useNav } from '@slidev/client'
import { computed } from 'vue'

const { currentSlideRoute } = useNav()

const currentFrontmatter = computed(() => {
  const route = currentSlideRoute.value
  return route?.meta?.slide?.frontmatter || route?.meta?.frontmatter
})

const hasRibbon = computed(() => !!currentFrontmatter.value?.ribbon)
const ribbonText = computed(() => currentFrontmatter.value?.ribbon || '')
const isTemplate = computed(() => ribbonText.value.toLowerCase() === 'template')
</script>

<template>
  <!-- 💡 style.cssのスタイルが自動適用されるため、HTMLの構造だけでOK -->
  <div v-if="hasRibbon" class="fixed top-0 left-0 w-full h-full pointer-events-none z-[999]">
    <div 
      class="cyber-ribbon" 
      :class="{ 'amber': isTemplate }"
    >
      {{ ribbonText }}
    </div>
  </div>
</template>
