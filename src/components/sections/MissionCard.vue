<script setup lang="ts">
defineProps<{
  icon: string
  title: string
}>()
</script>

<template>
  <div class="bg-primary-tint rounded-card p-10">
    <span class="mb-4 block text-3xl" aria-hidden="true">{{ icon }}</span>
    <h2 class="mb-4 text-2xl">{{ title }}</h2>
    <p class="text-text-muted text-base">
      <slot />
    </p>
  </div>
</template>
