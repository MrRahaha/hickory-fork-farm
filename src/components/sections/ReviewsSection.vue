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
  <section id="reviews" class="section reviews">
    <div class="container">
      <div class="section-header">
        <p class="eyebrow">Reviews</p>
        <h2>What our neighbors say</h2>
        <p>A few kind words from the folks we're lucky enough to feed.</p>
      </div>

      <div class="reviews__grid">
        <figure v-for="review in reviews" :key="review.name" class="review-card">
          <blockquote>&ldquo;{{ review.quote }}&rdquo;</blockquote>
          <figcaption>
            <span class="review-card__name">{{ review.name }}</span>
            <span class="review-card__detail">{{ review.detail }}</span>
          </figcaption>
        </figure>
      </div>
    </div>
  </section>
</template>

<style scoped>
.reviews__grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 1.75rem;
}

.review-card {
  background: var(--color-bg-alt);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.review-card blockquote {
  font-size: 1.02rem;
  color: var(--color-text);
  flex: 1;
}

.review-card figcaption {
  display: flex;
  flex-direction: column;
  font-size: 0.85rem;
}

.review-card__name {
  font-weight: 700;
  color: var(--color-primary-dark);
}

.review-card__detail {
  color: var(--color-text-muted);
}

@media (max-width: 860px) {
  .reviews__grid {
    grid-template-columns: 1fr;
  }
}
</style>
