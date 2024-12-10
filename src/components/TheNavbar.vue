<script setup>
import { ref } from 'vue'
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'

const scrollToSection = (id) => {
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <Disclosure as="nav" class="bg-secondary-light/80 backdrop-blur-sm fixed w-full z-50" v-slot="{ open }">
    <div class="container-width">
      <div class="relative flex h-24 items-center justify-between">
        <div class="flex items-center space-x-4">
          <img src="/logo.svg" alt="Synergize Logo" class="h-14 w-14" />
          <a href="#" class="text-3xl font-bold bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
            Synergize
          </a>
        </div>
        
        <!-- Desktop menu -->
        <div class="hidden md:block">
          <div class="flex items-center space-x-8">
            <button
              v-for="(section, index) in ['services', 'investments', 'contact']"
              :key="index"
              @click="scrollToSection(section)"
              class="text-lg text-gray-300 hover:text-primary transition-colors duration-200"
            >
              {{ section.charAt(0).toUpperCase() + section.slice(1) }}
            </button>
          </div>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <DisclosureButton class="text-gray-300 hover:text-primary transition-colors duration-200">
            <span class="sr-only">Open main menu</span>
            <svg class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path v-if="!open" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </DisclosureButton>
        </div>
      </div>
    </div>

    <!-- Mobile menu -->
    <DisclosurePanel class="md:hidden bg-secondary-light/90 backdrop-blur-sm">
      <div class="space-y-1 px-4 pb-3 pt-2">
        <button
          v-for="(section, index) in ['services', 'investments', 'contact']"
          :key="index"
          @click="scrollToSection(section)"
          class="block w-full text-left text-gray-300 hover:text-primary py-2 transition-colors duration-200 text-lg"
        >
          {{ section.charAt(0).toUpperCase() + section.slice(1) }}
        </button>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<style scoped>
.container-width {
  @apply max-w-7xl mx-auto px-4 sm:px-6 lg:px-8;
}
</style>
