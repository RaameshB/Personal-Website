<template>
  <footer class="mt-10 py-6 text-center text-sm text-gray-500 dark:text-gray-400 border-t border-gray-800 dark:border-gray-700">
    <p class="max-w-md mx-auto leading-relaxed">
    <span class="inline whitespace-nowrap">
        ML researcher who can train models but definitely cannot center a div.
    </span><br>
    Vibe-coded with Gemini + 
    <span class="inline-flex items-center gap-1">
        <a
        href="https://antigravity.google/"
        target="_blank"
        rel="noopener noreferrer"
        class="font-medium hover:underline"
        >
        antigravity
        </a>
        <Sparkles class="w-4 h-4" />
    </span>
    <span class="font-medium">
        (zero frontend skills were used • footer text conjured by 
        <a href="https://x.ai" target="_blank" rel="noopener noreferrer" class="hover:underline">Grok from xAI</a>)
    </span>
    </p>
  </footer>
</template>

<script setup lang="ts">
import { Sparkles } from 'lucide-vue-next'
</script>