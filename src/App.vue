<script setup>
import TheNavbar from './components/TheNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import InvestmentsSection from './components/InvestmentsSection.vue'
import ContactSection from './components/ContactSection.vue'
import NetworkAnimation from './components/NetworkAnimation.vue'
import MouseFollower from './components/MouseFollower.vue'
</script>

<template>
  <div class="min-h-screen relative">
    <MouseFollower />
    <NetworkAnimation />
    <TheNavbar />
    <main>
      <HeroSection />
      <ServicesSection />
      <InvestmentsSection />
      <ContactSection />
    </main>
  </div>
</template>