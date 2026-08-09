<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'
import logoMark from '@/assets/logo-mark.png'

const navLinks = [
  { id: 'story', label: 'Our Story' },
  { id: 'family', label: 'The Family' },
  { id: 'mission', label: 'Mission' },
  { id: 'products', label: 'Products' },
  { id: 'reviews', label: 'Reviews' },
  { id: 'contact', label: 'Contact' },
]

const isMenuOpen = ref(false)
const activeId = ref('')
let observer: IntersectionObserver | null = null

function closeMenu() {
  isMenuOpen.value = false
}

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}

onMounted(() => {
  const sections = navLinks
    .map((link) => document.getElementById(link.id))
    .filter((el): el is HTMLElement => el !== null)

  observer = new IntersectionObserver(
    (entries) => {
      const visible = entries
        .filter((entry) => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)

      if (visible[0]) {
        activeId.value = visible[0].target.id
      }
    },
    { rootMargin: '-40% 0px -50% 0px', threshold: [0, 0.25, 0.5, 0.75, 1] },
  )

  sections.forEach((section) => observer?.observe(section))
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>

<template>
  <header class="bg-bg/92 border-border sticky top-0 z-50 border-b backdrop-blur-sm">
    <div class="container flex h-18 items-center justify-between">
      <a href="#top" class="text-text flex items-center gap-3 no-underline" @click="closeMenu">
        <img
          :src="logoMark"
          alt=""
          class="size-9 shrink-0 object-contain sm:size-12"
          width="48"
          height="48"
        />
        <span
          class="text-primary-dark text-sm leading-tight font-bold whitespace-nowrap sm:text-base"
          >The Farm on Hickory Fork</span
        >
      </a>

      <button
        class="flex size-10 cursor-pointer flex-col justify-center gap-1 border-none bg-transparent md:hidden"
        type="button"
        :aria-expanded="isMenuOpen"
        aria-controls="primary-nav"
        aria-label="Toggle navigation menu"
        @click="toggleMenu"
      >
        <span class="bg-primary-dark block h-0.5 rounded-sm" />
        <span class="bg-primary-dark block h-0.5 rounded-sm" />
        <span class="bg-primary-dark block h-0.5 rounded-sm" />
      </button>

      <nav
        id="primary-nav"
        class="border-border bg-bg-alt absolute top-18 right-0 left-0 flex max-h-0 flex-col items-start gap-0 overflow-hidden border-b transition-all duration-300 md:static md:max-h-none md:flex-row md:items-center md:gap-7 md:overflow-visible md:border-b-0 md:bg-transparent"
        :class="{ 'max-h-96': isMenuOpen }"
      >
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          class="text-text after:bg-accent relative w-full px-6 py-4 text-base font-medium whitespace-nowrap no-underline after:absolute after:right-0 after:-bottom-1 after:left-0 after:hidden after:h-0.5 after:scale-x-0 after:transition-transform after:duration-200 after:content-[''] hover:after:scale-x-100 md:w-auto md:px-0 md:py-1 md:after:block"
          :class="{
            'bg-primary-tint text-primary-dark after:scale-x-100 md:bg-transparent':
              activeId === link.id,
          }"
          @click="closeMenu"
        >
          {{ link.label }}
        </a>
      </nav>
    </div>
  </header>
</template>
