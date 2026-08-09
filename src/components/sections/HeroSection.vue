<script setup lang="ts"></script>

<template>
  <section id="top" class="hero">
    <div class="hero__backdrop" aria-hidden="true" />
    <div class="container hero__inner">
      <p class="eyebrow eyebrow--light">A small family farm</p>
      <h1>The Farm on Hickory Fork</h1>
      <p class="hero__subtitle">
        Pasture-raised eggs, meat, and lamb &mdash; raised with care on our family's land and
        offered fresh to our neighbors and community.
      </p>
      <div class="hero__actions">
        <a href="#products" class="btn btn--primary">See What We Offer</a>
        <a href="#contact" class="btn btn--outline">Get In Touch</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  display: flex;
  align-items: center;
  min-height: 88vh;
  color: #fff;
  overflow: hidden;
  scroll-margin-top: 72px;
}

.hero__backdrop {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(circle at 15% 20%, rgba(255, 255, 255, 0.08), transparent 45%),
    linear-gradient(135deg, var(--color-primary-dark) 0%, var(--color-primary) 55%, #5a7248 100%);
  z-index: -1;
}

.hero__inner {
  padding-top: 3rem;
  padding-bottom: 3rem;
  max-width: 720px;
}

.eyebrow--light {
  color: #e9dfc4;
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 1rem;
}

.hero h1 {
  color: #fff;
  font-size: clamp(2.5rem, 1.9rem + 3vw, 4rem);
  margin-bottom: 1.25rem;
}

.hero__subtitle {
  font-size: 1.15rem;
  color: rgba(255, 255, 255, 0.88);
  max-width: 560px;
  margin-bottom: 2.25rem;
}

.hero__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

@media (max-width: 640px) {
  .hero {
    min-height: 80vh;
  }
}
</style>
