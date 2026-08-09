<script setup lang="ts">
import type { Component } from 'vue'
import SectionHeader from '@/components/SectionHeader.vue'
import FacebookIcon from '@/components/icons/FacebookIcon.vue'
import InstagramIcon from '@/components/icons/InstagramIcon.vue'
import NextdoorIcon from '@/components/icons/NextdoorIcon.vue'
import ContactCard from './ContactCard.vue'
import SocialLink from './SocialLink.vue'

interface ContactMethod {
  icon: string
  label: string
  value: string
  href: string
}

const methods: ContactMethod[] = [
  {
    icon: '📞',
    label: 'Call or Text',
    value: '(555) 867-5309',
    href: 'tel:+15558675309',
  },
  {
    icon: '✉️',
    label: 'Email',
    value: 'hello@thefarmonhickoryfork.com',
    href: 'mailto:hello@thefarmonhickoryfork.com',
  },
  {
    icon: '📍',
    label: 'Farm Location',
    value: '1245 Hickory Fork Road, Your Town, ST',
    href: 'https://maps.google.com',
  },
]

interface SocialLinkData {
  label: string
  href: string
  background: string
  icon: Component
}

const socialLinks: SocialLinkData[] = [
  {
    label: 'Facebook',
    href: 'https://facebook.com',
    background: '#0866ff',
    icon: FacebookIcon,
  },
  {
    label: 'Instagram',
    href: 'https://instagram.com',
    background: 'linear-gradient(45deg, #feda75, #fa7e1e, #d62976, #962fbf, #4f5bd5)',
    icon: InstagramIcon,
  },
  {
    label: 'Nextdoor',
    href: 'https://nextdoor.com',
    background: '#8ed500',
    icon: NextdoorIcon,
  },
]
</script>

<template>
  <section id="contact" class="section section--alt">
    <div class="container">
      <SectionHeader eyebrow="Contact" title="Get in touch">
        <p>Reach out about eggs, meat, or lamb &mdash; we'd love to hear from you.</p>
      </SectionHeader>

      <div class="mx-auto grid max-w-5xl grid-cols-1 gap-7 lg:grid-cols-3">
        <ContactCard v-for="method in methods" :key="method.label" v-bind="method" />
      </div>

      <div class="mt-12 flex flex-col items-center gap-3">
        <span class="text-text-muted text-sm font-semibold tracking-wider uppercase">
          Find us on
        </span>
        <div class="flex flex-wrap justify-center gap-3">
          <SocialLink v-for="social in socialLinks" :key="social.label" v-bind="social" />
        </div>
      </div>
    </div>
  </section>
</template>
