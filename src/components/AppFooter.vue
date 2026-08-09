<script setup lang="ts">
const year = new Date().getFullYear()
</script>

<template>
  <footer class="site-footer">
    <div class="container site-footer__inner">
      <p>&copy; {{ year }} The Farm on Hickory Fork. All rights reserved.</p>
      <p class="site-footer__note">Raised with care, right down the road.</p>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background: var(--color-primary-dark);
  color: rgba(255, 255, 255, 0.75);
}

.site-footer__inner {
  padding: 2rem 1.5rem;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
  font-size: 0.9rem;
}

.site-footer__note {
  color: rgba(255, 255, 255, 0.55);
}
</style>
