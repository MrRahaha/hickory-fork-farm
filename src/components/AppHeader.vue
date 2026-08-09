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
  <header class="bg-bg/92 border-border sticky top-0 z-50 border-b backdrop-blur-[8px]">
    <div class="container flex h-18 items-center justify-between">
      <a
        href="#top"
        class="text-text flex items-center gap-[0.7rem] no-underline"
        @click="closeMenu"
      >
        <img
          :src="logoMark"
          alt=""
          class="h-12 w-12 shrink-0 object-contain max-[480px]:h-9 max-[480px]:w-9"
          width="48"
          height="48"
        />
        <span
          class="text-primary-dark text-[1.05rem] leading-tight font-bold whitespace-nowrap max-[480px]:text-[0.85rem]"
          >The Farm on Hickory Fork</span
        >
      </a>

      <button
        class="hidden h-10 w-10 cursor-pointer flex-col justify-center gap-[5px] border-none bg-transparent max-[850px]:flex"
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
        class="flex items-center gap-7 max-[850px]:absolute max-[850px]:top-[72px] max-[850px]:right-0 max-[850px]:left-0 max-[850px]:max-h-0 max-[850px]:flex-col max-[850px]:items-start max-[850px]:gap-0 max-[850px]:overflow-hidden max-[850px]:border-b max-[850px]:transition-[max-height] max-[850px]:duration-[250ms] max-[850px]:bg-bg-alt max-[850px]:border-border"
        :class="{ 'max-[850px]:max-h-[400px]': isMenuOpen }"
      >
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          class="text-text after:bg-accent relative py-1 text-[0.95rem] font-medium whitespace-nowrap no-underline after:absolute after:right-0 after:-bottom-1 after:left-0 after:h-0.5 after:scale-x-0 after:transition-transform after:duration-200 after:content-[''] hover:after:scale-x-100 max-[850px]:w-full max-[850px]:px-6 max-[850px]:py-[0.9rem] max-[850px]:after:hidden"
          :class="{
            'text-primary-dark after:scale-x-100 max-[850px]:bg-primary-tint': activeId === link.id,
          }"
          @click="closeMenu"
        >
          {{ link.label }}
        </a>
      </nav>
    </div>
  </header>
</template>
