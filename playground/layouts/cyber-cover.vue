<template>
  <div class="slidev-layout bg-cyberpunk flex flex-col justify-center items-center h-full p-12 select-none">
    <!-- 装飾用のダミーバイナリ/ステータスバー -->
    <div class="absolute top-4 left-6 text-xs text-coolgray-500 font-mono flex gap-4">
      <span>[ STATUS: ONLINE ]</span>
      <span>[ OS: ARCH_LINUX_CYBER ]</span>
    </div>
    <div class="absolute top-4 right-6 text-xs text-neon-pink font-mono animate-pulse">
      ● CRITICAL_CORE_LOADED
    </div>

    <!-- メインコンテンツエリア -->
    <div class="cyber-border p-10 w-full max-w-3xl border-l-4 border-l-$cyber-pink">
      <!-- ターミナル風のプロンプト文字 -->
      <span class="text-neon-pink font-bold text-xl block mb-2">
        <slot name="command" />
      </span>      

      <!-- メインタイトル -->
      <h1 class="text-5xl font-extrabold tracking-wider text-neon-cyan mb-4 uppercase">
        <slot />
      </h1>
      
      <!-- サブタイトル（スロットで外部から注入） -->
      <div class="text-xl text-coolgray-300 font-mono tracking-wide border-t border-coolgray-800 pt-4 mt-4">
        <slot name="subtitle" />
      </div>
    </div>

    <!-- フッター装飾 -->
    <div class="absolute bottom-4 left-6 text-xs font-mono text-neon-cyan opacity-60">
      >> WARNING: SYSTEM ALTERED BY USER
    </div>
    <div class="absolute bottom-4 right-6 text-xs font-mono text-coolgray-500">
      SYS_REV: 2026.09 // AUTHOR_INIT
    </div>
  </div>
</template>
