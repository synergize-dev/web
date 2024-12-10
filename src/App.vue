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
  <div class="min-h-screen bg-black">
    <MouseFollower />
    <TheNavbar />
    <main class="bg-black">
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

<style>
/* Hide default cursor */
* {
  cursor: none;
}

/* Show cursor on interactive elements */
a, button, input, textarea, select {
  cursor: pointer !important;
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
  background-color: black;
}

body {
  background-color: black;
}

/* Ensure proper stacking */
.cursor {
  position: fixed !important;
  z-index: 999999 !important;
}
</style>
