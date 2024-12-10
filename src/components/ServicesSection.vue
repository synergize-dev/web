<script setup>
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
  <section id="services" class="section-padding bg-secondary-light">
    <div class="container-width">
      <h2 class="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
        Our Services
      </h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div v-for="service in services" 
             :key="service.title"
             class="p-6 rounded-xl bg-secondary hover:bg-secondary/80 transition-all duration-300 transform hover:-translate-y-1">
          <div class="text-4xl mb-4">{{ service.icon }}</div>
          <h3 class="text-xl font-bold mb-2 text-primary">{{ service.title }}</h3>
          <p class="text-gray-400">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>