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
  <section id="products" class="section section--alt products">
    <div class="container">
      <div class="section-header">
        <img
          :src="logoFull"
          alt="The Farm on Hickory Fork — Family Owned &amp; Operated, Est. 2020"
          class="products__logo"
          width="663"
          height="592"
        />
        <p class="eyebrow">Farm Products</p>
        <h2>Fresh from our farm to your table</h2>
        <p>Everything we raise is available directly from the farm &mdash; just ask.</p>
      </div>

      <div class="products__grid">
        <article v-for="item in offerings" :key="item.title" class="product-card">
          <span class="product-card__icon" aria-hidden="true" v-html="icons[item.icon]"></span>
          <h3>{{ item.title }}</h3>
          <p class="product-card__description">{{ item.description }}</p>
          <ul class="product-card__list">
            <li v-for="detail in item.details" :key="detail">{{ detail }}</li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.products__logo {
  width: 400px;
  height: auto;
  margin: 0 auto 1.5rem;
}

.products__grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 1.75rem;
}

.product-card {
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 2rem;
  transition:
    transform 0.15s ease,
    box-shadow 0.15s ease;
}

.product-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-md);
}

.product-card__icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 3.25rem;
  height: 3.25rem;
  border-radius: 50%;
  background: var(--color-primary-tint);
  color: var(--color-primary);
  margin-bottom: 1.25rem;
}

.product-card__icon :deep(svg) {
  width: 1.6rem;
  height: 1.6rem;
}

.product-card h3 {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.product-card__description {
  color: var(--color-text-muted);
  margin-bottom: 1.25rem;
}

.product-card__list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.product-card__list li {
  font-size: 0.9rem;
  color: var(--color-text);
  padding-left: 1.25rem;
  position: relative;
}

.product-card__list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-weight: 700;
}

/* Below the grid breakpoint, swap the single full-width column for a
   compact two-up grid so cards stay a readable width and the layout
   scales as more products are added. */
@media (max-width: 860px) {
  .products__grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }

  .product-card {
    padding: 1.25rem;
  }

  .product-card__icon {
    width: 2.5rem;
    height: 2.5rem;
    margin-bottom: 0.85rem;
  }

  .product-card__icon :deep(svg) {
    width: 1.25rem;
    height: 1.25rem;
  }

  .product-card h3 {
    font-size: 1.05rem;
    margin-bottom: 0.35rem;
  }

  .product-card__description {
    font-size: 0.85rem;
    margin-bottom: 0.85rem;
  }

  .product-card__list {
    gap: 0.4rem;
  }

  .product-card__list li {
    font-size: 0.78rem;
    padding-left: 1rem;
  }
}

/* On the smallest screens, two columns get too tight for the icon,
   title, description, and detail list — drop to a single column. */
@media (max-width: 640px) {
  .products__grid {
    grid-template-columns: 1fr;
  }

  .product-card {
    padding: 1.5rem;
  }

  .product-card__description {
    font-size: 0.9rem;
  }

  .product-card__list li {
    font-size: 0.85rem;
  }
}
</style>
