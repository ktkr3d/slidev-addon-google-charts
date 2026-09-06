<script setup lang="ts">
import { computed, useSlots } from 'vue'

const slots = useSlots()

// 💡 フッターの文字列を動的に判定するロジック
const footerText = computed(() => {
  // 1. もし「::footer::」スロットが明示的に指定されている場合
  if (slots.footer) {
    const footerContent = slots.footer()[0]?.children
    // 空文字（スペースなど）または文字が指定されている場合はそれを返す
    if (typeof footerContent === 'string') {
      return footerContent.trim()
    }
  }

  // 2. 「::footer::」の指定がなく、「::header::」がある場合は、タイトルから自動生成
  if (slots.header) {
    const headerContent = slots.header()[0]?.children
    if (typeof headerContent === 'string') {
      // 記号やスペースをサイバー風のアンダースコアに変換し、大文字化
      const formattedTitle = headerContent
        .trim()
        .replace(/[\s./:\-]+/g, '_') // スペースやドット、ハイフンを「_」に置換
        .toUpperCase()
      
      return `LAYER_${formattedTitle}`
    }
  }

  // 3. どちらもなければデフォルトのフォールバック値
  return 'SYSTEM_CONSOLE_ACTIVE'
})
</script>

<template>
  <div class="slidev-layout bg-cyberpunk h-full p-12 flex flex-col justify-between">
    <!-- ページ上部のタイトルエリア -->
    <div class="mb-4">
      <h2 class="text-3xl font-bold text-neon-cyan tracking-wider uppercase border-b border-coolgray-800 pb-2">
        <slot name="header" />
      </h2>
    </div>

    <!-- メインコンテンツ（中央配置の1カラム） -->
    <div class="my-auto w-full text-coolgray-200">
      <slot />
    </div>

    <!-- ページ下部のフッター -->
    <div class="text-xs text-coolgray-600 font-mono mt-4 flex justify-between border-t border-coolgray-900 pt-2">
      <span>:: {{ footerText }}</span>
      <!-- 前回の修正を反映した、エラーの起きないビルトインのページ番号 -->
      <span class="flex items-center gap-1">
        [ <SlideCurrentNo /> / <SlidesTotal /> ]
      </span>
    </div>
  </div>
</template>
