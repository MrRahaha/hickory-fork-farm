<script setup lang="ts"></script>

<template>
  <section
    id="top"
    class="relative flex min-h-[80vh] scroll-mt-[72px] items-center overflow-hidden text-white sm:min-h-[88vh]"
  >
    <div
      class="absolute inset-0 -z-10 bg-[radial-gradient(circle_at_15%_20%,rgba(255,255,255,.08),transparent_45%),linear-gradient(135deg,var(--color-primary-dark)_0%,var(--color-primary)_55%,#5a7248_100%)]"
      aria-hidden="true"
    />
    <div class="container max-w-[720px] py-12">
      <p class="eyebrow mb-4 text-[#e9dfc4]">A small family farm</p>
      <h1 class="mb-5 text-[clamp(2.5rem,1.9rem+3vw,4rem)] text-white">The Farm on Hickory Fork</h1>
      <p class="mb-9 max-w-[560px] text-[1.15rem] text-white/88">
        Pasture-raised eggs, meat, and lamb &mdash; raised with care on our family's land and
        offered fresh to our neighbors and community.
      </p>
      <div class="flex flex-wrap gap-4">
        <a href="#products" class="btn btn--primary">See What We Offer</a>
        <a href="#contact" class="btn btn--outline">Get In Touch</a>
      </div>
    </div>
  </section>
</template>
