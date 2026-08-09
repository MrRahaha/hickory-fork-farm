<script setup lang="ts">
defineProps<{
  icon: string
  label: string
  value: string
  href: string
}>()
</script>

<template>
  <a
    :href="href"
    class="bg-bg border-border rounded-card text-text flex flex-col items-center gap-2 border px-6 py-8 text-center no-underline transition hover:-translate-y-1 hover:shadow-md"
    target="_blank"
    rel="noopener"
  >
    <span class="mb-2 text-3xl" aria-hidden="true">{{ icon }}</span>
    <span class="text-primary-dark text-base font-bold">{{ label }}</span>
    <span class="text-text-muted text-sm">{{ value }}</span>
  </a>
</template>
