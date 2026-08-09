<script setup lang="ts">
defineProps<{
  quote: string
  name: string
  detail: string
}>()
</script>

<template>
  <figure class="bg-bg-alt border-border rounded-card flex flex-col gap-6 border p-8">
    <blockquote class="text-text flex-1 text-base">&ldquo;{{ quote }}&rdquo;</blockquote>
    <figcaption class="flex flex-col text-sm">
      <span class="text-primary-dark font-bold">{{ name }}</span>
      <span class="text-text-muted">{{ detail }}</span>
    </figcaption>
  </figure>
</template>
