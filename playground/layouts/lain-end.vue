<script setup lang="ts">
import { computed, useSlots } from 'vue'

const slots = useSlots()

// 💡 フッターの文字列を動的に判定するロジック（lain風に少しひねりを追加）
const footerText = computed(() => {
  // 1. もし「::footer::」が明示的に指定されている場合（空文字含む）
  if (slots.footer) {
    const footerContent = slots.footer()?.children
    if (typeof footerContent === 'string') {
      return footerContent.trim()
    }
  }

  // 2. 「::footer::」がなく、スライド内にテキスト（見出しなど）がある場合はそこから抽出
  if (slots.default) {
    // 仮想DOM(VNode)の中から最初に見つかったテキスト要素を探す
    const firstNode = slots.default().find(node => typeof node.children === 'string')
    if (firstNode && typeof firstNode.children === 'string') {
      const parsedText = firstNode.children
        .trim()
        .replace(/[\s./:\-]+/g, '_') // 記号やスペースを「_」に置換
        .toUpperCase()
      
      return `LAYER_${parsedText}`
    }
  }

  // 3. 何もなければlainの原作リスペクトのデフォルト設定
  return 'LAYER_♾️_END_OF_TRANSMISSION'
})
</script>

<template>
  <div class="slidev-layout bg-lain flex flex-col justify-center items-center h-full p-12 select-none relative">
    
    <!-- 有線LANのハミング/ノイズをイメージした背景の巨大な影文字 -->
    <div class="absolute inset-0 flex justify-center items-center opacity-5 pointer-events-none select-none">
      <span class="text-[12rem] font-bold tracking-tighter text-white font-mono">WIRED</span>
    </div>

    <!-- メインメッセージエリア -->
    <div class="lain-text-group text-center z-10">
      <!-- 
        💡 slots.default を配置。
        これにより、Markdownに直接書いた文字がここにレンダリングされます 
      -->
      <slot />

      <p class="lain-title text-2xl md:text-3xl font-light uppercase mb-2">
        Present Day,
      </p>
      <p class="lain-title text-2xl md:text-3xl font-light uppercase mb-8">
        Present Time...
      </p>
      
      <!-- 不気味な笑い声 -->
      <p class="lain-laugh text-xl font-bold uppercase tracking-widest animate-pulse">
        HAHAHAHAHA...
      </p>
    </div>

    <!-- ページ下部のフッター（cyber-two-cols と構造を完全統一！） -->
    <div class="absolute bottom-4 left-6 right-6 text-xs text-neutral-700 font-mono flex justify-between border-t border-neutral-900 pt-2 z-20">
      <!-- 💡 footerText が空文字（""）の時は非表示、あれば表示 -->
      <span v-if="footerText">:: {{ footerText }}</span>
      <span v-else></span>
      
      <span class="flex items-center gap-1 text-neutral-600">
        [ <SlideCurrentNo /> / <SlidesTotal /> ]
      </span>
    </div>
  </div>
</template>
