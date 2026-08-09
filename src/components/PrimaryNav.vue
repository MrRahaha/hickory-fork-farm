<script setup lang="ts">
defineProps<{
  links: { id: string; label: string }[]
  activeId: string
  isOpen: boolean
}>()

defineEmits<{
  navigate: []
}>()
</script>

<template>
  <nav
    id="primary-nav"
    class="border-border bg-bg-alt absolute top-18 right-0 left-0 flex max-h-0 flex-col items-start gap-0 overflow-hidden border-b transition-all duration-300 md:static md:max-h-none md:flex-row md:items-center md:gap-7 md:overflow-visible md:border-b-0 md:bg-transparent"
    :class="{ 'max-h-96': isOpen }"
  >
    <a
      v-for="link in links"
      :key="link.id"
      :href="`#${link.id}`"
      class="text-text after:bg-accent relative w-full px-6 py-4 text-base font-medium whitespace-nowrap no-underline after:absolute after:right-0 after:-bottom-1 after:left-0 after:hidden after:h-0.5 after:scale-x-0 after:transition-transform after:duration-200 after:content-[''] hover:after:scale-x-100 md:w-auto md:px-0 md:py-1 md:after:block"
      :class="{
        'bg-primary-tint text-primary-dark after:scale-x-100 md:bg-transparent':
          activeId === link.id,
      }"
      @click="$emit('navigate')"
    >
      {{ link.label }}
    </a>
  </nav>
</template>
