<script setup lang="ts"></script>

<template>
  <section id="story" class="section">
    <div
      class="container grid grid-cols-[1fr_1.2fr] items-center gap-14 max-[800px]:grid-cols-1 max-[800px]:gap-8"
    >
      <div
        class="max-[800px]:order-first max-[800px]:mx-auto max-[800px]:max-w-[280px]"
        aria-hidden="true"
      >
        <div
          class="rounded-card shadow-md flex aspect-[4/5] items-center justify-center bg-[linear-gradient(160deg,var(--color-primary-tint)_0%,#ded4b0_100%)]"
        >
          <span class="text-[4rem]">🌾</span>
        </div>
      </div>

      <div>
        <p class="eyebrow">Our Story</p>
        <h2 class="mb-5 text-[clamp(1.75rem,1.4rem+1.5vw,2.4rem)]">
          Rooted in this land, raised by hand
        </h2>
        <p class="text-text-muted mb-4 text-[1.05rem] last:mb-0">
          The Farm on Hickory Fork started as a small backyard flock and a big idea: that our
          neighbors deserved better access to real food, raised close to home. What began with a
          handful of hens has grown into a working hobby farm producing eggs, meat, and lamb &mdash;
          all raised the slow way, on pasture, without shortcuts.
        </p>
        <p class="text-text-muted mb-4 text-[1.05rem] last:mb-0">
          We're not a big operation, and we like it that way. Every animal on this farm is cared for
          by hand, every day, by us. It's more work, but it's the only way we know how to do it
          right.
        </p>
      </div>
    </div>
  </section>
</template>
