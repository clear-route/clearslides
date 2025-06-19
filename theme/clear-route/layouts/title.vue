<template>
  <div class="slidev-layout title-slide relative h-full w-full" :style="{ background: 'var(--gradient-title-slide)' }">
    <div class="absolute left-16 top-1/2 -translate-y-1/2 w-3/5">
      <slot name="default" />
    </div>
    <div class="absolute bottom-10 left-16">
      <slot name="logo">
        <Logo name="logo-landscape" height="h-20" />
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