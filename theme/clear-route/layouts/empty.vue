<template>
  <div class="slidev-layout generic-slide relative h-full w-full" :style="{ background: backgroundGradient }">
    <div class="w-full h-full flex items-top justify-left p-8">
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

</style>