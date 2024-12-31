<script setup>
import SectionWithNetwork from './layout/SectionWithNetwork.vue'

const services = [
  {
    title: 'Secure e-voting Solutions',
    description: 'As a Vocdoni certified integrator partner, we specialize in implementing secure and transparent blockchain-based voting systems. Our solutions ensure voter privacy, verifiable results, and seamless integration with existing platforms.',
    icon: '/vocdoni.svg',
    isVocdoni: true
  },
  {
    title: 'Blockchain Architecture & Decentralized Systems',
    description: 'Expert guidance in designing scalable blockchain systems and high-performance distributed architectures. Leveraging our deep expertise in GoLang and distributed systems, we build efficient, secure, and maintainable solutions that optimize resource utilization while ensuring robust system integrity.',
    icon: '⚡'
  },
  {
    title: 'Secure & Private Cryptographic Systems',
    description: 'Implementation of advanced cryptographic solutions including zkSNARK technology for privacy-preserving applications. We design and develop secure systems that protect sensitive data while maintaining transparency where needed, enabling trust through mathematical proof systems.',
    icon: '🔐'
  },
  {
    title: 'Open Source Consultation',
    description: 'Strategic advice on open source development, community building, and ecosystem growth. We help organizations navigate the open source landscape, from choosing licenses to building contributor communities and maintaining sustainable projects.',
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
      <div class="flex flex-col gap-6 max-w-4xl mx-auto">
        <div v-for="service in services" 
             :key="service.title"
             :class="[
               'p-8 rounded-xl backdrop-blur-sm transition-all duration-300 transform hover:-translate-x-2',
               service.isVocdoni 
                 ? 'bg-secondary/70 hover:bg-secondary/80 border-2 border-primary shadow-lg' 
                 : 'bg-secondary/50 hover:bg-secondary/60'
             ]">
          <div class="text-4xl mb-4">
            <img v-if="service.isVocdoni" :src="service.icon" alt="Vocdoni Logo" class="h-12 w-auto" />
            <span v-else>{{ service.icon }}</span>
          </div>
          <h3 class="text-xl font-bold mb-2 text-primary">{{ service.title }}</h3>
          <p class="text-gray-300">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </SectionWithNetwork>
</template>
