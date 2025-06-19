<template>
  <svg viewBox="0 0 100 100" preserveAspectRatio="xMidYMid meet" class="h-full w-full">
    <defs>
      <linearGradient id="veeGradient" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" stop-color="#8A63D2" /> <!-- Darker purple approximation -->
        <stop offset="100%" :stop-color="`var(--clear-route-purple)`" />
      </linearGradient>
    </defs>
    <path d="M0 0 L50 100 L100 0 L80 0 L50 60 L20 0 Z" fill="url(#veeGradient)" />
  </svg>
</template>

<script setup>
// No script needed for a static SVG component
</script>