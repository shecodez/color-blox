<script setup lang="ts">
import { Color } from '@/utils/colors';

defineProps<{
  css: string | number;
  color?: Color | string;
}>();
</script>

<template>
  <div class="blox" :class="`b-${css} bg-${color}`" @click="$emit('clicked')">
    <slot></slot>
  </div>
</template>

<style scoped>
.blox {
  cursor: pointer;

  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.5);

  border-radius: 0.25rem; /* 4px */
}
</style>
