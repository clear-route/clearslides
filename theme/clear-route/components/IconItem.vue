<template>
  <div class="flex items-center gap-6">
    <img :src="icon" alt="Icon" class="w-12 h-12 flex-shrink-0" />
    <p class="text-white">{{ text }}</p>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  icon: {
    type: String,
    required: true,
  },
  text: {
    type: String,
    required: true,
  },
});
</script>

<style scoped>
/* Add any specific styles if needed, but Tailwind should handle most */
</style>