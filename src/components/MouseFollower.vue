<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useMouse } from '@vueuse/core'

const cursor = ref(null)
const { x, y } = useMouse()

const updateCursor = () => {
  if (!cursor.value) return
  cursor.value.style.transform = `translate(${x.value}px, ${y.value}px)`
}

onMounted(() => {
  if (cursor.value) {
    window.addEventListener('mousemove', updateCursor)
  }
})

onUnmounted(() => {
  window.removeEventListener('mousemove', updateCursor)
})
</script>

<template>
  <div ref="cursor" class="cursor-follower">
    <div class="cursor-circle"></div>
    <div class="cursor-trail"></div>
  </div>
</template>

<style scoped>
.cursor-follower {
  pointer-events: none;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 9999;
  will-change: transform;
}

.cursor-circle {
  width: 24px;
  height: 24px;
  border: 2px solid #6366f1;
  border-radius: 50%;
  position: absolute;
  top: -12px;
  left: -12px;
  animation: pulse 2s infinite;
}

.cursor-trail {
  width: 100px;
  height: 100px;
  background: radial-gradient(circle, rgba(99, 102, 241, 0.1) 0%, rgba(99, 102, 241, 0) 70%);
  border-radius: 50%;
  position: absolute;
  top: -50px;
  left: -50px;
  opacity: 0.6;
}

@keyframes pulse {
  0% { transform: scale(1); opacity: 0.8; }
  50% { transform: scale(1.5); opacity: 0.4; }
  100% { transform: scale(1); opacity: 0.8; }
}
</style>