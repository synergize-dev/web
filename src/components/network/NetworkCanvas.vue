<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const uniqueId = 'gradient-' + Math.random().toString(36).substr(2, 9);
const lines = ref([]);
const animationFrame = ref(null);

// Initialize lines
const initLines = () => {
  const lineCount = 25;
  lines.value = Array.from({ length: lineCount }, () => ({
    x1: Math.random() * 100,
    y1: Math.random() * 100,
    x2: Math.random() * 100,
    y2: Math.random() * 100,
    speedX1: (Math.random() - 0.5) * 0.2,
    speedY1: (Math.random() - 0.5) * 0.2,
    speedX2: (Math.random() - 0.5) * 0.2,
    speedY2: (Math.random() - 0.5) * 0.2,
    opacity: 0.5 + Math.random() * 0.3
  }));
};

// Update line positions
const updateLines = () => {
  lines.value.forEach(line => {
    // Update positions
    line.x1 += line.speedX1;
    line.y1 += line.speedY1;
    line.x2 += line.speedX2;
    line.y2 += line.speedY2;

    // Bounce off edges
    if (line.x1 <= 0 || line.x1 >= 100) {
      line.speedX1 *= -1;
      line.x1 = Math.max(0, Math.min(100, line.x1));
    }
    if (line.y1 <= 0 || line.y1 >= 100) {
      line.speedY1 *= -1;
      line.y1 = Math.max(0, Math.min(100, line.y1));
    }
    if (line.x2 <= 0 || line.x2 >= 100) {
      line.speedX2 *= -1;
      line.x2 = Math.max(0, Math.min(100, line.x2));
    }
    if (line.y2 <= 0 || line.y2 >= 100) {
      line.speedY2 *= -1;
      line.y2 = Math.max(0, Math.min(100, line.y2));
    }
  });

  animationFrame.value = requestAnimationFrame(updateLines);
};

onMounted(() => {
  initLines();
  updateLines();
});

onUnmounted(() => {
  if (animationFrame.value) {
    cancelAnimationFrame(animationFrame.value);
  }
});
</script>

<template>
  <div class="absolute inset-0 w-full h-full">
    <svg class="absolute inset-0 w-full h-full" viewBox="0 0 100 100">
      <defs>
        <linearGradient :id="uniqueId" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" stop-color="rgb(99, 102, 241)" stop-opacity="0.6" />
          <stop offset="100%" stop-color="rgb(34, 211, 238)" stop-opacity="0.6" />
        </linearGradient>
      </defs>
      <g class="lines-group">
        <line v-for="(line, index) in lines"
              :key="index"
              :x1="line.x1"
              :y1="line.y1"
              :x2="line.x2"
              :y2="line.y2"
              class="animated-line"
              :style="{
                opacity: line.opacity,
                stroke: `url(#${uniqueId})`
              }" />
      </g>
    </svg>
  </div>
</template>

<style scoped>
.animated-line {
  stroke-width: 0.5;
  vector-effect: non-scaling-stroke;
  will-change: transform;
}

.lines-group {
  mix-blend-mode: screen;
  filter: drop-shadow(0 0 2px rgba(99, 102, 241, 0.5));
}

svg {
  transform: scale(1.1);
  will-change: transform;
}
</style>
