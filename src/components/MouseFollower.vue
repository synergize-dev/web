<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const cursor = ref(null)
let mouseX = 0
let mouseY = 0

const onMouseMove = (e) => {
  mouseX = e.clientX
  mouseY = e.clientY
  if (cursor.value) {
    cursor.value.style.transform = `translate3d(${mouseX}px, ${mouseY}px, 0)`
  }
}

onMounted(() => {
  document.addEventListener('mousemove', onMouseMove, { passive: true })
})

onUnmounted(() => {
  document.removeEventListener('mousemove', onMouseMove)
})
</script>

<template>
  <div ref="cursor" class="cursor">
    <div class="cursor-dot"></div>
  </div>
</template>

<style scoped>
.cursor {
  position: fixed;
  top: -4px;
  left: -4px;
  z-index: 999999;
  pointer-events: none;
  will-change: transform;
  transform-style: preserve-3d;
}

.cursor-dot {
  width: 8px;
  height: 8px;
  background: #9333ea;
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(147, 51, 234, 0.5);
}
</style>
