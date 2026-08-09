<script setup lang="ts">
defineProps<{
  eyebrow: string
  title: string
}>()
</script>

<template>
  <div class="section-header">
    <slot name="before" />
    <p class="eyebrow">{{ eyebrow }}</p>
    <h2>{{ title }}</h2>
    <slot />
  </div>
</template>
