<template>
  <div class="slidev-layout section-title-slide relative h-full w-full" :style="{ background: backgroundGradient }">
    <div class="absolute left-[-2rem] top-0 h-full w-2/5">
      <img :src="props.imageSrc" class="h-full w-full object-contain" />
    </div>
    <div class="absolute right-16 top-1/2 -translate-y-1/2 w-1/2">
      <h2 class="text-4xl uppercase font-bold m-0 p-0" :style="{ fontFamily: 'var(--font-heading)', color: primaryColor }">
        <slot name="phase" />
      </h2>
      <h1 class="text-5xl uppercase font-bold text-clear-route-white m-0 p-0" :style="{ fontFamily: 'var(--font-heading)' }">
        <slot name="main-heading" />
      </h1>
      <h3 class="text-md uppercase font-bold mt-4 m-0 p-0" :style="{ fontFamily: 'var(--font-heading)', color: primaryColor }">
        <slot name="sub-heading" />
      </h3>
      <div class="text-clear-route-white mt-4 whitespace-pre-wrap space-y-4">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  imageSrc: {
    type: String,
    default: '/icons/Pilot.svg', // Default image
  },
  backgroundGradient: {
    type: String,
    default: 'var(--gradient-dark-to-purple)', // Default gradient
  },
  primaryColor: {
    type: String,
    default: 'var(--clear-route-purple)', // Default primary color
  }
})
</script>