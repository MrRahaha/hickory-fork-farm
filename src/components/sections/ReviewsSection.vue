<script setup lang="ts">
import SectionHeader from '@/components/SectionHeader.vue'
import ReviewCard from './ReviewCard.vue'

interface Review {
  quote: string
  name: string
  detail: string
}

const reviews: Review[] = [
  {
    quote:
      "Best eggs we've ever had, hands down. Once you try farm-fresh you can't go back to the store.",
    name: 'Karen M.',
    detail: 'Weekly egg customer',
  },
  {
    quote:
      'We reserved a half lamb this year and it was worth every penny. Tom and Sarah were great to work with from start to finish.',
    name: 'Dave R.',
    detail: 'Neighbor & repeat customer',
  },
  {
    quote:
      "It's so nice knowing exactly where our food comes from and who raised it. This farm has become part of our routine.",
    name: 'The Alvarez Family',
    detail: 'Local customers',
  },
]
</script>

<template>
  <section id="reviews" class="section">
    <div class="container">
      <SectionHeader eyebrow="Reviews" title="What our neighbors say">
        <p>A few kind words from the folks we're lucky enough to feed.</p>
      </SectionHeader>

      <div class="grid grid-cols-1 gap-7 lg:grid-cols-3">
        <ReviewCard v-for="review in reviews" :key="review.name" v-bind="review" />
      </div>
    </div>
  </section>
</template>
