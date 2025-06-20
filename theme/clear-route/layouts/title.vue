<template>
  <div class="slidev-layout title-slide relative h-full w-full" :style="{ background: 'var(--gradient-dark-to-green)' }">
    <div class="absolute left-16 top-1/2 -translate-y-1/2 w-3/5">
      <h2 class="text-5xl uppercase font-bold m-0 p-0" :style="{ fontFamily: 'var(--font-heading)', lineHeight: '0.9' }">
        <slot name="heading" />
      </h2>
      <h3 class="text-md text-clear-route-white uppercase font-bold m-0 p-0 mt-2" :style="{ fontFamily: 'var(--font-heading)' }">
        <slot name="subheading" />
      </h3>
      <p class="text-md text-clear-route-white m-0 mt-2 p-0" :style="{ fontFamily: 'var(--font-body)' }">
        <slot name="date" />
      </p>
    </div>
    <div class="absolute bottom-10 left-16">
      <slot name="logo">
        <Logo name="logo-landscape" height="h-15" />
      </slot>
    </div>
    <div class="absolute right-0 top-0 h-full w-2/5">
      <!-- Placeholder for geometric shapes, can be replaced with SVG or more complex CSS later -->
    </div>
  </div>
</template>

<script setup>
import Logo from '../components/Logo.vue'
</script>