<script setup lang="ts">
import type { Component } from 'vue'
import { Beef, Egg, Flower2 } from '@lucide/vue'
import logoFull from '@/assets/logo-full.png'
import SectionHeader from '@/components/SectionHeader.vue'
import BreadIcon from '@/components/icons/BreadIcon.vue'
import HoneyIcon from '@/components/icons/HoneyIcon.vue'
import LambIcon from '@/components/icons/LambIcon.vue'
import ProductCard from './ProductCard.vue'

interface Offering {
  icon: Component
  title: string
  description: string
  details: string[]
}

const offerings: Offering[] = [
  {
    icon: Egg,
    title: 'Fresh Eggs',
    description: 'Free-range eggs from a happy, pasture-raised flock, gathered daily.',
    details: [
      'Available year-round',
      'By the dozen or half-dozen',
      'Farm pickup or local delivery',
    ],
  },
  {
    icon: Beef,
    title: 'Pasture-Raised Meat',
    description: 'Chicken and pork raised slowly on open pasture, processed locally.',
    details: ['Whole and half orders', 'Seasonal availability', 'Ask about bulk pricing'],
  },
  {
    icon: LambIcon,
    title: 'Lamb',
    description: 'Grass-fed lamb raised in small batches for the best flavor and quality.',
    details: ['Whole, half, or cuts', 'Limited seasonal batches', 'Reserve ahead of harvest'],
  },
  {
    icon: BreadIcon,
    title: 'Bakery',
    description: 'Sourdough, biscuits, and bread baked fresh in small batches.',
    details: ['Baked weekly', 'Sourdough, biscuits & bread', 'Farm pickup or local delivery'],
  },
  {
    icon: Flower2,
    title: 'Flowers',
    description: 'Cut flowers grown and gathered right here on the farm.',
    details: ['Available in spring', 'Marigolds, daisies & more', 'Farm pickup or local delivery'],
  },
  {
    icon: HoneyIcon,
    title: 'Honey',
    description: 'Raw, unfiltered honey from our own hives.',
    details: ['Available seasonally', 'By the jar', 'Farm pickup or local delivery'],
  },
]
</script>

<template>
  <section id="products" class="section section--alt">
    <div class="container">
      <SectionHeader eyebrow="Farm Products" title="Fresh from our farm to your table">
        <template #before>
          <img
            :src="logoFull"
            alt="The Farm on Hickory Fork — Family Owned &amp; Operated, Est. 2020"
            class="mx-auto mb-6 h-auto w-96"
            width="663"
            height="592"
          />
        </template>
        <p>Everything we raise is available directly from the farm &mdash; just ask.</p>
      </SectionHeader>

      <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-3 lg:gap-7">
        <ProductCard v-for="item in offerings" :key="item.title" v-bind="item" />
      </div>
    </div>
  </section>
</template>
