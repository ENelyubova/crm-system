<script setup lang="ts">
import type { HTMLAttributes } from 'vue'
import { cn } from '@/utils/utils'

const props = defineProps<{
  class?: HTMLAttributes['class']
}>()
</script>

<template>
  <div
    class="card"
    :class="
      cn(
        'rounded-lg text-card-foreground animation border border-transparent transition-colors hover:border-[#a252c83d]',
        props.class,
      )
    "
  >
    <slot />
  </div>
</template>

<style scoped>
.card {
  backdrop-filter: blur(23px);
  box-shadow: 0 51px 69px 0 rgba(23, 18, 43, 0.59);
  background: linear-gradient(216deg, rgba(41, 39, 85, 0.35) 0%, rgba(41, 39, 84, 0.78) 49.65%, rgba(27, 24, 66, 0.35) 100%);
}

@keyframes show {
  from {
    @aplly border-[#a252c83d];
    transform: scale(.5) translateY(-30px);
  }

  90% {
    @apply border-[#a252c83d];
  }

  to {
    @apply border-transparent;
  }
}

.animation {
  animation: show .3s ease-in-out;
}
</style>
