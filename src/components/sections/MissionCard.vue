<script setup lang="ts">
import type { Component } from 'vue'

defineProps<{
  icon: Component
  title: string
}>()
</script>

<template>
  <div class="bg-primary-tint rounded-card p-10">
    <component :is="icon" class="text-primary mb-4 size-8" aria-hidden="true" />
    <h2 class="mb-4 text-2xl">{{ title }}</h2>
    <p class="text-text-muted text-base">
      <slot />
    </p>
  </div>
</template>
