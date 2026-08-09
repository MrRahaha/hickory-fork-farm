<script setup lang="ts">
import logoFull from '@/assets/logo-full.png'

interface Offering {
  icon: string
  title: string
  description: string
  details: string[]
}

const icons: Record<string, string> = {
  egg: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2.5C8.5 7 6 11.2 6 14.5a6 6 0 0 0 12 0C18 11.2 15.5 7 12 2.5Z"/></svg>',
  meat: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M13.5 3.8a4.2 4.2 0 0 1 6 6L13 16.3a5 5 0 1 1-6-6l6.5-6.5Z"/><path d="M9.2 15.8 4 21"/></svg>',
  lamb: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M7.5 9.2c-1.6-1.3-3.3-.6-3.3 1s1.4 2.4 2.8 2"/><path d="M16.5 9.2c1.6-1.3 3.3-.6 3.3 1s-1.4 2.4-2.8 2"/><circle cx="12" cy="11.5" r="5.2"/><path d="M9.8 20.5 9.3 17.3"/><path d="M14.2 20.5 14.7 17.3"/></svg>',
}

const offerings: Offering[] = [
  {
    icon: 'egg',
    title: 'Fresh Eggs',
    description: 'Free-range eggs from a happy, pasture-raised flock, gathered daily.',
    details: [
      'Available year-round',
      'By the dozen or half-dozen',
      'Farm pickup or local delivery',
    ],
  },
  {
    icon: 'meat',
    title: 'Pasture-Raised Meat',
    description: 'Chicken and pork raised slowly on open pasture, processed locally.',
    details: ['Whole and half orders', 'Seasonal availability', 'Ask about bulk pricing'],
  },
  {
    icon: 'lamb',
    title: 'Lamb',
    description: 'Grass-fed lamb raised in small batches for the best flavor and quality.',
    details: ['Whole, half, or cuts', 'Limited seasonal batches', 'Reserve ahead of harvest'],
  },
]
</script>

<template>
  <section id="products" class="section section--alt">
    <div class="container">
      <div class="section-header">
        <img
          :src="logoFull"
          alt="The Farm on Hickory Fork — Family Owned &amp; Operated, Est. 2020"
          class="mx-auto mb-6 h-auto w-96"
          width="663"
          height="592"
        />
        <p class="eyebrow">Farm Products</p>
        <h2>Fresh from our farm to your table</h2>
        <p>Everything we raise is available directly from the farm &mdash; just ask.</p>
      </div>

      <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-3 lg:gap-7">
        <article
          v-for="item in offerings"
          :key="item.title"
          class="bg-bg border-border rounded-card border p-6 transition hover:-translate-y-1 hover:shadow-md sm:p-5 lg:p-8"
        >
          <span
            class="bg-primary-tint text-primary mb-3 inline-flex size-10 items-center justify-center rounded-full [&_svg]:size-5 lg:mb-5 lg:size-13 lg:[&_svg]:size-6"
            aria-hidden="true"
            v-html="icons[item.icon]"
          ></span>
          <h3 class="mb-1 text-base lg:mb-2 lg:text-xl">
            {{ item.title }}
          </h3>
          <p class="text-text-muted mb-3 text-sm lg:mb-5 lg:text-base">
            {{ item.description }}
          </p>
          <ul class="flex list-none flex-col gap-2">
            <li
              v-for="detail in item.details"
              :key="detail"
              class="text-text before:text-primary relative pl-4 text-sm before:absolute before:left-0 before:font-bold before:content-['✓'] sm:text-xs lg:pl-5"
            >
              {{ detail }}
            </li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>
