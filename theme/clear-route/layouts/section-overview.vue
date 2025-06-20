<template>
  <div class="slidev-layout section-overview-slide relative h-full w-full" :style="{ background: backgroundGradient }">
    <div class="absolute right-[-3rem] top-0 h-full w-1/2">
      <img :src="imageSrc" class="h-full w-full object-contain" />
    </div>
    <div class="absolute left-16 top-1/2 -translate-y-1/2 w-1/2">
      <h3 class="text-md text-clear-route-white uppercase font-bold m-0 p-0 mb-2" :style="{ fontFamily: 'var(--font-body)' }">
        <slot name="caption" />
      </h3>
      <h2 class="text-4xl uppercase font-bold m-0 p-0" :style="{ fontFamily: 'var(--font-heading)', lineHeight: '0.9' }">
        <slot name="heading" />
      </h2>
      <div class="body-content mt-4" :style="{ color: bodyColor, fontFamily: 'var(--font-body)' }">
        <slot name="body" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  imageSrc: {
    type: String,
    default: '/graphics/09.svg', // Default image from user's request
  },
  backgroundGradient: {
    type: String,
    default: 'var(--clear-route-grey-dark)', // Default gradient
  },
  bodyColor: {
    type: String,
    default: 'var(--clear-route-white)', // Default body text color
  }
})
</script>
