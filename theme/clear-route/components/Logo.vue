<script setup>
import { computed } from 'vue'

const props = defineProps({
  name: {
    type: String,
    default: 'logo-landscape', // Default logo for dark backgrounds
  },
  height: {
    type: String,
    default: 'h-10', // Default height
  }
})

const logoSrc = computed(() => `/logos/${props.name}.png`)
</script>

<template>
  <div>
    <img :src="logoSrc" :class="height" />
  </div>
</template>