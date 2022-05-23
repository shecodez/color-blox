<template>
  <div class="blox-grid">
    <slot></slot>
  </div>
</template>

<style scoped>
.blox-grid {
  flex: 1;
  height: 100%;

  background-color: #ccc;
  color: white;

  display: grid;
  grid-gap: 10px;
}
</style>
