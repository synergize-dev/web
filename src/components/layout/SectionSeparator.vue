<template>
  <div class="section-separator relative h-24 overflow-hidden">
    <div class="absolute inset-0 flex items-center justify-center">
      <!-- Glowing line -->
      <div class="w-full h-px bg-gradient-to-r from-transparent via-primary to-transparent animate-glow"></div>
      
      <!-- Decorative elements -->
      <div class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2">
        <div class="w-12 h-12 relative">
          <!-- Central dot -->
          <div class="absolute inset-5 bg-primary rounded-full animate-pulse"></div>
          
          <!-- Orbiting particles -->
          <div class="absolute inset-0 animate-spin-slow">
            <div class="absolute top-0 left-1/2 -translate-x-1/2 w-2 h-2 bg-accent rounded-full"></div>
            <div class="absolute bottom-0 left-1/2 -translate-x-1/2 w-2 h-2 bg-accent rounded-full"></div>
          </div>
          <div class="absolute inset-0 animate-spin-slow-reverse">
            <div class="absolute left-0 top-1/2 -translate-y-1/2 w-2 h-2 bg-primary rounded-full"></div>
            <div class="absolute right-0 top-1/2 -translate-y-1/2 w-2 h-2 bg-primary rounded-full"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes glow {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 1; }
}

@keyframes spin-slow {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes spin-slow-reverse {
  from { transform: rotate(360deg); }
  to { transform: rotate(0deg); }
}

.animate-glow {
  animation: glow 3s ease-in-out infinite;
}

.animate-spin-slow {
  animation: spin-slow 8s linear infinite;
}

.animate-spin-slow-reverse {
  animation: spin-slow-reverse 8s linear infinite;
}
</style>
