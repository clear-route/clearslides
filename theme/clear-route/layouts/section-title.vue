<template>
  <div class="slidev-layout content-v-slide relative h-full w-full" :style="{ background: 'var(--gradient-dark-to-purple)' }">
    <div class="absolute left-[-2rem] top-0 h-full w-2/5">
      <img src="/icons/Pilot.svg" class="h-full w-full object-contain" />
    </div>
    <div class="absolute right-16 top-1/2 -translate-y-1/2 w-1/2">
      <h2 class="text-4xl uppercase font-bold text-clear-route-purple m-0 p-0" :style="{ fontFamily: 'var(--font-heading)' }">
        <slot name="phase" />
      </h2>
      <h1 class="text-5xl uppercase font-bold text-clear-route-white m-0 p-0" :style="{ fontFamily: 'var(--font-heading)' }">
        <slot name="main-heading" />
      </h1>
      <h3 class="text-md uppercase font-bold text-clear-route-purple mt-4 m-0 p-0" :style="{ fontFamily: 'var(--font-heading)' }">
        <slot name="sub-heading" />
      </h3>
      <div class="text-clear-route-white mt-4 whitespace-pre-wrap">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
// No specific imports needed for a direct image
</script>