<script setup lang="ts">
import type { Component } from 'vue'

defineProps<{
  icon: Component
  title: string
  description: string
  details: string[]
}>()
</script>

<template>
  <article
    class="bg-bg border-border rounded-card border p-6 transition hover:-translate-y-1 hover:shadow-md sm:p-5 lg:p-8"
  >
    <span
      class="bg-primary-tint text-primary mb-3 inline-flex size-10 items-center justify-center rounded-full lg:mb-5 lg:size-13"
      aria-hidden="true"
    >
      <component :is="icon" class="size-5 lg:size-6" />
    </span>
    <h3 class="mb-1 text-base lg:mb-2 lg:text-xl">
      {{ title }}
    </h3>
    <p class="text-text-muted mb-3 text-sm lg:mb-5 lg:text-base">
      {{ description }}
    </p>
    <ul class="flex list-none flex-col gap-2">
      <li
        v-for="detail in details"
        :key="detail"
        class="text-text before:text-primary relative pl-4 text-sm before:absolute before:left-0 before:font-bold before:content-['✓'] sm:text-xs lg:pl-5"
      >
        {{ detail }}
      </li>
    </ul>
  </article>
</template>
