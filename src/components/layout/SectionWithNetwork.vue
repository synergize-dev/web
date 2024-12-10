<script setup>
import NetworkCanvas from '../network/NetworkCanvas.vue'

defineProps({
  id: {
    type: String,
    default: ''
  },
  class: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <section :id="id" class="section-padding relative overflow-hidden" :class="class">
    <NetworkCanvas />
    <div class="relative z-10">
      <slot></slot>
    </div>
  </section>
</template>

<style scoped>
.section-padding {
  padding: 6rem 0;
}
</style>
