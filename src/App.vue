<template>
  <TheNavbar />
  <main class="pt-[70px]">
    <RouterView />
  </main>
  <footer class="bg-[#1b1b1b] h-[70px] flex items-center justify-center">
    <p class="font-mono text-sm text-muted">Copyright © 2025 Peter Kysel ❤️</p>
  </footer>
</template>

<script setup lang="ts">
import TheNavbar from './components/TheNavbar.vue'
</script>
