<script setup lang="ts"></script>

<template>
  <section id="story" class="section story">
    <div class="container story__grid">
      <div class="story__media" aria-hidden="true">
        <div class="story__media-inner">
          <span class="story__media-icon">🌾</span>
        </div>
      </div>

      <div class="story__content">
        <p class="eyebrow">Our Story</p>
        <h2>Rooted in this land, raised by hand</h2>
        <p>
          The Farm on Hickory Fork started as a small backyard flock and a big idea: that our
          neighbors deserved better access to real food, raised close to home. What began with a
          handful of hens has grown into a working hobby farm producing eggs, meat, and lamb &mdash;
          all raised the slow way, on pasture, without shortcuts.
        </p>
        <p>
          We're not a big operation, and we like it that way. Every animal on this farm is cared for
          by hand, every day, by us. It's more work, but it's the only way we know how to do it
          right.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.story__grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 3.5rem;
  align-items: center;
}

.story__media-inner {
  aspect-ratio: 4 / 5;
  border-radius: var(--radius);
  background: linear-gradient(160deg, var(--color-primary-tint) 0%, #ded4b0 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: var(--shadow-md);
}

.story__media-icon {
  font-size: 4rem;
}

.story__content h2 {
  font-size: clamp(1.75rem, 1.4rem + 1.5vw, 2.4rem);
  margin-bottom: 1.25rem;
}

.story__content p {
  color: var(--color-text-muted);
  margin-bottom: 1rem;
  font-size: 1.05rem;
}

.story__content p:last-child {
  margin-bottom: 0;
}

@media (max-width: 800px) {
  .story__grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .story__media {
    order: -1;
    max-width: 280px;
    margin: 0 auto;
  }
}
</style>
