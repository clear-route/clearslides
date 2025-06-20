<template>
    <div class="slidev-layout section-three-column-slide relative w-full h-full" :style="{ background: backgroundGradient }">
        <div class="mx-8 pt-8">
            <h1 class="text-2xl uppercase font-bold m-0 p-0 whitespace-pre-wrap" :style="{ fontFamily: 'var(--font-heading)', lineHeight: '0.9' }">
                <slot name="heading" />
            </h1>
        </div>
        <div class="w-full h-full flex" :class="getVerticalAlignmentClass(verticalAlignment)">
          <div class="grid grid-cols-3 gap-4 px-8 py-6 pb-26">
              <div class="col-span-1">
                  <slot name="left" />
              </div>
              <div class="col-span-1">
                  <slot name="center" />
              </div>
              <div class="col-span-1">
                  <slot name="right" />
              </div>
          </div>
        </div>
    </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  backgroundGradient: {
    type: String,
    default: 'var(--clear-route-grey-dark)', // Default gradient
  },
  verticalAlignment: {
    type: String,
    default: 'center', // Default vertical alignment, can be 'top', 'center', or 'bottom'
  },
})

// Function to map prop value to Tailwind CSS class
const getVerticalAlignmentClass = (align) => {
  switch (align) {
    case 'top':
      return 'items-start';
    case 'center':
      return 'items-center';
    case 'bottom':
      return 'items-end';
    default:
      return 'items-center';
  }
};
</script>
