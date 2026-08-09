<script setup lang="ts">
const year = new Date().getFullYear()
</script>

<template>
  <footer class="bg-primary-dark text-white/75">
    <div class="container flex flex-wrap items-center justify-between gap-2 py-8 text-sm">
      <p>&copy; {{ year }} The Farm on Hickory Fork. All rights reserved.</p>
      <p class="text-white/55">Raised with care, right down the road.</p>
    </div>
  </footer>
</template>
