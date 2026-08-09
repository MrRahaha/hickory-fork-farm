<script setup lang="ts">
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import HeroSection from './components/sections/HeroSection.vue'
import StorySection from './components/sections/StorySection.vue'
import BiosSection from './components/sections/BiosSection.vue'
import MissionSection from './components/sections/MissionSection.vue'
import ServicesSection from './components/sections/ServicesSection.vue'
import ReviewsSection from './components/sections/ReviewsSection.vue'
import ContactSection from './components/sections/ContactSection.vue'
</script>

<template>
  <AppHeader />
  <main>
    <HeroSection />
    <StorySection />
    <BiosSection />
    <MissionSection />
    <ServicesSection />
    <ReviewsSection />
    <ContactSection />
  </main>
  <AppFooter />
</template>
