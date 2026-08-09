<script setup lang="ts">
import { ref } from 'vue'
import logoMark from '@/assets/logo-mark.png'
import { useScrollSpy } from '@/composables/useScrollSpy'
import NavToggle from './NavToggle.vue'
import PrimaryNav from './PrimaryNav.vue'

const navLinks = [
  { id: 'story', label: 'Our Story' },
  { id: 'family', label: 'The Family' },
  { id: 'mission', label: 'Mission' },
  { id: 'products', label: 'Products' },
  { id: 'reviews', label: 'Reviews' },
  { id: 'contact', label: 'Contact' },
]

const { activeId } = useScrollSpy(navLinks.map((link) => link.id))
const isMenuOpen = ref(false)

function closeMenu() {
  isMenuOpen.value = false
}

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}
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

      <NavToggle :is-open="isMenuOpen" @toggle="toggleMenu" />
      <PrimaryNav
        :links="navLinks"
        :active-id="activeId"
        :is-open="isMenuOpen"
        @navigate="closeMenu"
      />
    </div>
  </header>
</template>
