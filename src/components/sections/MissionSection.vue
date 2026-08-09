<script setup lang="ts">
import MissionCard from './MissionCard.vue'
</script>

<template>
  <section id="mission" class="section">
    <div class="container">
      <div class="grid grid-cols-1 gap-8 md:grid-cols-2">
        <MissionCard icon="🌱" title="Our Mission">
          To raise honest, pasture-based food and share it directly with the families in our
          community &mdash; treating our animals, our land, and our neighbors with the same care
          we'd want for our own table.
        </MissionCard>

        <MissionCard icon="🌤️" title="Our Vision">
          A neighborhood where good food doesn't have to travel far to be trusted &mdash; where you
          know the hands that raised it, and the land it came from.
        </MissionCard>
      </div>
    </div>
  </section>
</template>
