<script setup lang="ts">
import type { HTMLAttributes } from 'vue'
import { cn } from '@/lib/utils'

const props = defineProps<{
  class?: HTMLAttributes['class']
}>()
</script>

<template>
  <div :class="cn(
    'rounded-xl border bg-card text-card-foreground shadow',
    props.class,
  )
    ">
    <slot />
  </div>
</template>

<style scoped>
div:hover {
  border-color: var(--primary);
  border-width: 1px;
  transition: 300ms;
}
div{
  transition: 300ms;
}
</style>