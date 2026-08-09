<script setup lang="ts">
defineProps<{
  isOpen: boolean
}>()

defineEmits<{
  toggle: []
}>()
</script>

<template>
  <button
    class="flex size-10 cursor-pointer flex-col justify-center gap-1 border-none bg-transparent md:hidden"
    type="button"
    :aria-expanded="isOpen"
    aria-controls="primary-nav"
    aria-label="Toggle navigation menu"
    @click="$emit('toggle')"
  >
    <span class="bg-primary-dark block h-0.5 rounded-sm" />
    <span class="bg-primary-dark block h-0.5 rounded-sm" />
    <span class="bg-primary-dark block h-0.5 rounded-sm" />
  </button>
</template>
