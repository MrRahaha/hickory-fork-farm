<script setup lang="ts">
import type { Component } from 'vue'

defineProps<{
  href: string
  label: string
  background: string
  icon: Component
}>()
</script>

<template>
  <a
    :href="href"
    class="border-border bg-bg text-primary-dark inline-flex items-center gap-2 rounded-full border px-5 py-2 text-sm font-semibold no-underline transition hover:-translate-y-0.5 hover:shadow-sm"
    target="_blank"
    rel="noopener"
  >
    <span
      class="inline-flex size-6 shrink-0 items-center justify-center rounded-full"
      :style="{ background }"
    >
      <component :is="icon" class="size-3.5" />
    </span>
    {{ label }}
  </a>
</template>
