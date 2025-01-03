<script setup>
import SectionWithNetwork from './layout/SectionWithNetwork.vue'

const investments = [
  {
    title: 'Decentralized Education',
    description: 'Supporting initiatives that democratize blockchain education worldwide. We empower underserved communities with knowledge and tools to participate in the decentralized future.',
    icon: '📚'
  },
  {
    title: 'Environmental Impact',
    description: 'Investing in sustainable blockchain solutions and carbon-neutral protocols. We prioritize projects that leverage technology to address climate change and environmental challenges.',
    icon: '🌱'
  },
  {
    title: 'Financial Inclusion',
    description: 'Backing innovative DeFi projects that provide essential financial services to unbanked and underbanked populations, fostering economic empowerment and equality.',
    icon: '💫'
  }
]
</script>

<template>
  <SectionWithNetwork id="investments">
    <div class="container-width relative z-10">
      <div class="text-center mb-12">
        <h2 class="text-3xl font-bold mb-4 bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
          Impact Investments
        </h2>
        <p class="text-base md:text-lg text-gray-300 max-w-3xl mx-auto">
          We invest in early-stage projects that align with our vision of a more equitable, 
          decentralized future. Our focus is on initiatives that create lasting social impact.
        </p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8">
        <div v-for="investment in investments" 
             :key="investment.title"
             class="p-6 rounded-xl backdrop-blur-sm transition-all duration-500 cursor-pointer bg-secondary/70 hover:bg-secondary/90 border-2 border-primary hover:border-accent hover:scale-[1.02] hover:translate-x-2 hover:shadow-[0_0_30px_rgba(var(--primary-rgb),0.3)]">
          <div class="text-3xl mb-3 transition-transform duration-500 group-hover:scale-110">{{ investment.icon }}</div>
          <h3 class="text-lg font-bold mb-2 text-primary hover:text-accent transition-colors duration-500">{{ investment.title }}</h3>
          <p class="text-sm md:text-base text-gray-300 transition-colors duration-500 group-hover:text-gray-200">{{ investment.description }}</p>
        </div>
      </div>
    </div>
  </SectionWithNetwork>
</template>
