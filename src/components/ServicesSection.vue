<script setup>
import SectionWithNetwork from './layout/SectionWithNetwork.vue'

const services = [
  {
    title: 'Blockchain Architecture',
    description: 'Expert guidance in designing scalable and secure blockchain systems',
    icon: '🔗'
  },
  {
    title: 'zkSNARK Development',
    description: 'Implementation of zero-knowledge proofs for privacy-preserving applications',
    icon: '🔐'
  },
  {
    title: 'Efficient Decentralized Systems',
    description: 'Building high-performance distributed systems with optimal resource utilization',
    icon: '⚡'
  },
  {
    title: 'Open Source Consultation',
    description: 'Strategic advice on open source development and community building',
    icon: '🌐'
  }
]
</script>

<template>
  <SectionWithNetwork id="services">
    <div class="container-width relative z-10">
      <h2 class="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
        Our Services
      </h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div v-for="service in services" 
             :key="service.title"
             class="p-6 rounded-xl backdrop-blur-sm bg-secondary/50 hover:bg-secondary/60 transition-all duration-300 transform hover:-translate-y-1">
          <div class="text-4xl mb-4">{{ service.icon }}</div>
          <h3 class="text-xl font-bold mb-2 text-primary">{{ service.title }}</h3>
          <p class="text-gray-300">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </SectionWithNetwork>
</template>
