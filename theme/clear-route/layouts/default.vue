<template>
  <div class="slidev-layout default-slide relative h-full w-full" :style="{ background: 'var(--gradient-content-slide)' }">
    <div class="absolute left-0 top-0 h-full w-2/5">
      <!-- Placeholder for the large 'V' shape, can be replaced with SVG or more complex CSS later -->
    </div>
    <div class="absolute right-16 top-1/2 -translate-y-1/2 w-3/5">
      <slot />
    </div>
  </div>
</template>