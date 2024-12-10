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
        <div class="logo-container mb-8">
          <img src="/logo.png" alt="Synergize Logo" class="mx-auto w-32 h-32 object-contain animate-logo hover:scale-105 transition-transform duration-300" />
        </div>
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

@keyframes logoAppear {
  0% {
    opacity: 0;
    transform: translateY(50px) scale(0.3);
    filter: blur(20px) brightness(0);
  }
  40% {
    opacity: 0.6;
    transform: translateY(-20px) scale(1.2);
    filter: blur(10px) brightness(1.2);
  }
  60% {
    opacity: 0.8;
    transform: translateY(10px) scale(0.9);
    filter: blur(5px) brightness(1);
  }
  80% {
    transform: translateY(-5px) scale(1.1);
    filter: blur(0) brightness(1.1);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
    filter: blur(0) brightness(1);
  }
}

.animate-logo {
  opacity: 0;
  animation: logoAppear 2s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
  filter: drop-shadow(0 0 15px rgba(255, 255, 255, 0.3));
}

.logo-container img {
  will-change: transform, opacity, filter;
}

@keyframes pulse {
  0%, 100% { 
    box-shadow: 0 0 15px rgba(255, 255, 255, 0.15);
  }
  50% { 
    box-shadow: 0 0 25px rgba(255, 255, 255, 0.25);
  }
}

.logo-container {
  animation: pulse 3s ease-in-out infinite;
  border-radius: 50%;
  padding: 0.5rem;
  display: inline-block;
}
</style>
