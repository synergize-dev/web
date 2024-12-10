<script setup>
import TheNavbar from './components/TheNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import InvestmentsSection from './components/InvestmentsSection.vue'
import ContactSection from './components/ContactSection.vue'
import MouseFollower from './components/MouseFollower.vue'
import SectionSeparator from './components/layout/SectionSeparator.vue'
</script>

<template>
  <div class="min-h-screen relative bg-black">
    <MouseFollower />
    <TheNavbar />
    <main>
      <HeroSection />
      <SectionSeparator />
      <ServicesSection />
      <SectionSeparator />
      <InvestmentsSection />
      <SectionSeparator />
      <ContactSection />
    </main>
  </div>
</template>
