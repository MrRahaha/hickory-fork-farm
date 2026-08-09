<script setup lang="ts">
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
      <div class="section-header">
        <p class="eyebrow">Reviews</p>
        <h2>What our neighbors say</h2>
        <p>A few kind words from the folks we're lucky enough to feed.</p>
      </div>

      <div class="grid grid-cols-1 gap-7 min-[861px]:grid-cols-3">
        <figure
          v-for="review in reviews"
          :key="review.name"
          class="bg-bg-alt border-border rounded-card flex flex-col gap-6 border p-8"
        >
          <blockquote class="text-text flex-1 text-[1.02rem]">
            &ldquo;{{ review.quote }}&rdquo;
          </blockquote>
          <figcaption class="flex flex-col text-[0.85rem]">
            <span class="text-primary-dark font-bold">{{ review.name }}</span>
            <span class="text-text-muted">{{ review.detail }}</span>
          </figcaption>
        </figure>
      </div>
    </div>
  </section>
</template>
