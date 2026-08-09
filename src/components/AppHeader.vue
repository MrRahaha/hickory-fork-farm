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
  <header class="site-header">
    <div class="container site-header__inner">
      <a href="#top" class="brand" @click="closeMenu">
        <img :src="logoMark" alt="" class="brand__mark" width="48" height="48" />
        <span class="brand__name">The Farm on Hickory Fork</span>
      </a>

      <button
        class="nav-toggle"
        type="button"
        :aria-expanded="isMenuOpen"
        aria-controls="primary-nav"
        aria-label="Toggle navigation menu"
        @click="toggleMenu"
      >
        <span class="nav-toggle__bar" />
        <span class="nav-toggle__bar" />
        <span class="nav-toggle__bar" />
      </button>

      <nav id="primary-nav" class="nav" :class="{ 'nav--open': isMenuOpen }">
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          class="nav__link"
          :class="{ 'nav__link--active': activeId === link.id }"
          @click="closeMenu"
        >
          {{ link.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.site-header {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(250, 248, 243, 0.92);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--color-border);
}

.site-header__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 72px;
}

.brand {
  display: flex;
  align-items: center;
  gap: 0.7rem;
  text-decoration: none;
  color: var(--color-text);
}

.brand__mark {
  width: 48px;
  height: 48px;
  object-fit: contain;
  flex-shrink: 0;
}

.brand__name {
  font-weight: 700;
  font-size: 1.05rem;
  line-height: 1.2;
  color: var(--color-primary-dark);
  white-space: nowrap;
}

.nav {
  display: flex;
  align-items: center;
  gap: 1.75rem;
}

.nav__link {
  position: relative;
  text-decoration: none;
  color: var(--color-text);
  font-size: 0.95rem;
  font-weight: 500;
  padding: 0.25rem 0;
  white-space: nowrap;
}

.nav__link::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: -4px;
  height: 2px;
  background: var(--color-accent);
  transform: scaleX(0);
  transition: transform 0.2s ease;
}

.nav__link:hover::after,
.nav__link--active::after {
  transform: scaleX(1);
}

.nav__link--active {
  color: var(--color-primary-dark);
}

.nav-toggle {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 40px;
  height: 40px;
  background: transparent;
  border: none;
  cursor: pointer;
}

.nav-toggle__bar {
  display: block;
  height: 2px;
  background: var(--color-primary-dark);
  border-radius: 2px;
}

@media (max-width: 480px) {
  .brand__name {
    font-size: 0.85rem;
  }

  .brand__mark {
    width: 36px;
    height: 36px;
  }
}

@media (max-width: 850px) {
  .nav-toggle {
    display: flex;
  }

  .nav {
    position: absolute;
    top: 72px;
    left: 0;
    right: 0;
    background: var(--color-bg-alt);
    border-bottom: 1px solid var(--color-border);
    flex-direction: column;
    align-items: flex-start;
    gap: 0;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.25s ease;
  }

  .nav--open {
    max-height: 400px;
  }

  .nav__link {
    width: 100%;
    padding: 0.9rem 1.5rem;
  }

  .nav__link::after {
    display: none;
  }

  .nav__link--active {
    background: var(--color-primary-tint);
  }
}
</style>
