<script setup>
import TheNavbar from './components/TheNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import InvestmentsSection from './components/InvestmentsSection.vue'
import ContactSection from './components/ContactSection.vue'
import SectionSeparator from './components/layout/SectionSeparator.vue'
</script>

<template>
  <div class="min-h-screen bg-black">
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
/* Smooth scrolling */
html {
  scroll-behavior: smooth;
  background-color: black;
}

body {
  background-color: black;
}

</style>
