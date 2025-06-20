<template>
  <div class="slidev-layout generic-header-slide relative h-full w-full" :style="{ background: backgroundGradient }">
    <div class="mx-8 py-8">
      <h1 class="text-2xl uppercase font-bold m-0 p-0 whitespace-pre-wrap" :style="{ fontFamily: 'var(--font-heading)', lineHeight: '0.9' }">
        <slot name="heading" />
      </h1>
    </div>
    <div class="w-full h-full flex items-top justify-left mx-8">
      <!-- This is the empty body section where users can add their content -->
      <div class="body-content" :style="{ color: bodyColor }">
        <slot name="body" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  backgroundGradient: {
    type: String,
    default: 'var(--gradient-dark-to-purple)', // Default gradient
  },
  bodyColor: {
    type: String,
    default: 'var(--clear-route-white)', // Default body text color
  }
})
</script>

<style scoped>
.body-content {
  text-align: left; 
}
</style>