<script setup lang="ts"></script>

<template>
  <section id="mission" class="section mission">
    <div class="container">
      <div class="mission__grid">
        <div class="mission-card">
          <span class="mission-card__icon" aria-hidden="true">🌱</span>
          <h2>Our Mission</h2>
          <p>
            To raise honest, pasture-based food and share it directly with the families in our
            community &mdash; treating our animals, our land, and our neighbors with the same care
            we'd want for our own table.
          </p>
        </div>

        <div class="mission-card">
          <span class="mission-card__icon" aria-hidden="true">🌤️</span>
          <h2>Our Vision</h2>
          <p>
            A neighborhood where good food doesn't have to travel far to be trusted &mdash; where
            you know the hands that raised it, and the land it came from.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.mission__grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 2rem;
}

.mission-card {
  background: var(--color-primary-tint);
  border-radius: var(--radius);
  padding: 2.5rem;
}

.mission-card__icon {
  font-size: 2rem;
  display: block;
  margin-bottom: 1rem;
}

.mission-card h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.mission-card p {
  color: var(--color-text-muted);
  font-size: 1.05rem;
}

@media (max-width: 700px) {
  .mission__grid {
    grid-template-columns: 1fr;
  }
}
</style>
