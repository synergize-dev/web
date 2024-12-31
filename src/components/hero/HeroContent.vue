<template>
  <div class="container-width relative z-10">
    <div class="max-w-5xl mx-auto text-center">
      <div class="logo-container mt-16 mb-4">
        <img src="/logo.svg" alt="Synergize Logo" class="mx-auto w-24 h-24 object-contain animate-logo hover:scale-105 transition-transform duration-300" />
      </div>
      <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold mt-12 mb-12 pb-8 min-h-[160px] animate-glow bg-gradient-to-r from-primary via-accent to-primary bg-clip-text text-transparent leading-relaxed bg-[length:200%_auto] hover:animate-shine relative">
        Pioneering Decentralized Technologies
      </h1>
      <div class="backdrop-blur-sm bg-secondary-light/30 rounded-2xl p-8 border border-primary/10 shadow-xl">
        <div class="space-y-6">
          <p class="text-base md:text-lg text-gray-200">
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
</template>

<style scoped>
@keyframes glow {
  0%, 100% {
    filter: drop-shadow(0 0 25px rgba(var(--primary-rgb), 0.5));
    text-shadow: 
      0 0 30px rgba(var(--primary-rgb), 0.5),
      0 0 60px rgba(var(--primary-rgb), 0.3),
      0 0 90px rgba(var(--primary-rgb), 0.2);
  }
  50% {
    filter: drop-shadow(0 0 40px rgba(var(--primary-rgb), 0.7));
    text-shadow: 
      0 0 50px rgba(var(--primary-rgb), 0.7),
      0 0 80px rgba(var(--primary-rgb), 0.5),
      0 0 120px rgba(var(--primary-rgb), 0.3);
  }
}

@keyframes shine {
  from {
    background-position: 0% center;
  }
  to {
    background-position: -200% center;
  }
}

.animate-glow {
  animation: glow 4s ease-in-out infinite;
}

.animate-shine:hover {
  animation: shine 3s linear infinite;
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
