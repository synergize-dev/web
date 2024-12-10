<script setup>
const particles = Array.from({ length: 20 }, (_, i) => ({
  id: i,
  x: Math.random() * 100,
  y: Math.random() * 100,
  size: Math.random() * 2 + 1
}))
</script>

<template>
  <section class="relative min-h-screen flex items-center justify-center section-padding hex-pattern overflow-hidden">
    <div class="container-width relative z-10">
      <div class="max-w-5xl mx-auto text-center">
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent leading-tight">
          Pioneering Decentralized Technologies
        </h1>
        <div class="backdrop-blur-sm bg-secondary-light/30 rounded-2xl p-8 border border-primary/10 shadow-xl">
          <div class="space-y-6">
            <p class="text-xl text-gray-200">
              Shaping the future of digital infrastructure through innovative decentralized solutions. 
              With 14 years of expertise, we transform visionary ideas into robust, scalable systems.
            </p>
            <p class="text-xl text-gray-200">
              Committed to Self-Sovereign technology, we empower organizations to achieve true digital 
              autonomy while maintaining complete ownership of their identity and data.
            </p>
          </div>
        </div>
        <div class="flex justify-center mt-12">
          <a href="#contact" class="btn-primary text-lg transform hover:scale-105 transition-transform duration-200">
            Get in Touch
          </a>
        </div>
      </div>
    </div>
    
    <!-- Animated particles -->
    <div v-for="particle in particles" 
         :key="particle.id"
         class="absolute bg-primary/20 rounded-full"
         :style="{
           width: particle.size + 'px',
           height: particle.size + 'px',
           left: particle.x + '%',
           top: particle.y + '%',
           animation: `float ${3 + Math.random() * 4}s infinite ease-in-out`
         }"
    />
  </section>
</template>

<style scoped>
@keyframes float {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(20px, -20px); }
}
</style>