<script setup>
const investments = [
  {
    title: 'Decentralized Education',
    description: 'Supporting initiatives that make blockchain education accessible to underserved communities worldwide.',
    icon: '📚'
  },
  {
    title: 'Environmental Impact',
    description: 'Investing in energy-efficient blockchain solutions and carbon-neutral protocols.',
    icon: '🌱'
  },
  {
    title: 'Financial Inclusion',
    description: 'Backing projects that bring DeFi solutions to unbanked and underbanked populations.',
    icon: '💫'
  }
]
</script>

<template>
  <section id="investments" class="section-padding bg-secondary relative overflow-hidden">
    <div class="container-width">
      <div class="text-center mb-16">
        <h2 class="text-4xl font-bold mb-6 bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
          Impact Investments
        </h2>
        <p class="text-xl text-gray-300 max-w-3xl mx-auto">
          We invest in early-stage projects that align with our vision of a more equitable, 
          decentralized future. Our focus is on initiatives that create lasting social impact.
        </p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8">
        <div v-for="investment in investments" 
             :key="investment.title"
             class="p-6 rounded-xl bg-secondary-light hover:bg-secondary-light/80 transition-all duration-300 transform hover:-translate-y-1">
          <div class="text-4xl mb-4">{{ investment.icon }}</div>
          <h3 class="text-xl font-bold mb-3 text-primary">{{ investment.title }}</h3>
          <p class="text-gray-400">{{ investment.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>