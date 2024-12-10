<script setup>
import { onMounted, ref } from 'vue'
import { useRafFn } from '@vueuse/core'
import { gsap } from 'gsap'

const canvas = ref(null)
let ctx
const nodes = []
const connections = []
const NODE_COUNT = 30
const CONNECTION_DISTANCE = 150
const NODE_SPEED = 0.5

class Node {
  constructor(x, y) {
    this.x = x
    this.y = y
    this.vx = (Math.random() - 0.5) * NODE_SPEED
    this.vy = (Math.random() - 0.5) * NODE_SPEED
    this.radius = Math.random() * 2 + 1
  }

  update(width, height) {
    this.x += this.vx
    this.y += this.vy

    if (this.x < 0 || this.x > width) this.vx *= -1
    if (this.y < 0 || this.y > height) this.vy *= -1
  }
}

function initCanvas() {
  if (!canvas.value) return
  ctx = canvas.value.getContext('2d')
  
  const resize = () => {
    canvas.value.width = window.innerWidth
    canvas.value.height = window.innerHeight
  }
  
  window.addEventListener('resize', resize)
  resize()

  // Initialize nodes
  for (let i = 0; i < NODE_COUNT; i++) {
    nodes.push(new Node(
      Math.random() * canvas.value.width,
      Math.random() * canvas.value.height
    ))
  }
}

function draw() {
  if (!ctx || !canvas.value) return

  ctx.clearRect(0, 0, canvas.value.width, canvas.value.height)
  
  // Update and draw nodes
  nodes.forEach(node => {
    node.update(canvas.value.width, canvas.value.height)
    
    ctx.beginPath()
    ctx.arc(node.x, node.y, node.radius, 0, Math.PI * 2)
    ctx.fillStyle = '#6366f1'
    ctx.fill()
  })

  // Draw connections
  ctx.strokeStyle = '#6366f120'
  nodes.forEach((node1, i) => {
    nodes.slice(i + 1).forEach(node2 => {
      const dx = node2.x - node1.x
      const dy = node2.y - node1.y
      const distance = Math.sqrt(dx * dx + dy * dy)
      
      if (distance < CONNECTION_DISTANCE) {
        ctx.beginPath()
        ctx.moveTo(node1.x, node1.y)
        ctx.lineTo(node2.x, node2.y)
        ctx.lineWidth = 1 - distance / CONNECTION_DISTANCE
        ctx.stroke()
      }
    })
  })
}

onMounted(() => {
  initCanvas()
  useRafFn(draw)
})
</script>

<template>
  <canvas
    ref="canvas"
    class="fixed inset-0 pointer-events-none"
  />
</template>