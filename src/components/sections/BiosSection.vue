<script setup lang="ts">
import SectionHeader from '@/components/SectionHeader.vue'
</script>

<template>
  <section id="family" class="section section--alt">
    <div class="container">
      <SectionHeader eyebrow="Meet the Family" title="The people behind the farm">
        <p>A husband-and-wife team doing this one chore, one season, at a time.</p>
      </SectionHeader>

      <div class="mx-auto max-w-3xl text-center">
        <div class="rounded-card shadow-md mb-8 overflow-hidden">
          <img
            src="/katiekyle.jpg"
            alt="Katie and Kyle Spruill standing in front of The Farm on Hickory Fork sign"
            class="aspect-[3/2] w-full object-cover object-[center_25%]"
          />
        </div>

        <h3 class="mb-1 text-2xl">Katie &amp; Kyle Spruill</h3>
        <p class="text-accent-dark mb-5 text-base font-semibold">Owners &amp; Operators</p>
        <p class="text-text-muted text-base">
          Katie and Kyle are the husband-and-wife team behind The Farm on Hickory Fork. Kyle handles
          the flock, the lambing, and anything that needs fixing &mdash; which, on a farm, is always
          something. Katie keeps the farm running day to day, from planning and record-keeping to
          getting eggs and orders into neighbors' hands. Together they've built a small operation
          they're proud to put their name on, and they love the relationships it's built with the
          folks who eat what they raise.
        </p>
      </div>
    </div>
  </section>
</template>
