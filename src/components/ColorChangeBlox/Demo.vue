<script setup lang="ts">
import { ref } from 'vue';
import { colors } from '@/utils/colors';

import Grid from '@/components/Grid.vue';
import Blox from '@/components/Blox.vue';

// 2 rows x 4 cols (3x5 lines)
const grid1 = ref([
  { id: 1, color: colors[10] },
  { id: 2, color: colors[17] },
  { id: 3, color: colors[2] },
  { id: 4, color: colors[16] },
]);

// 3 rows x 3 cols (4x4 lines)
const grid2 = ref([
  { id: 5, color: colors[14] },
  { id: 6, color: colors[8] },
  { id: 7, color: colors[7] },
  { id: 8, color: colors[12] },
  { id: 9, color: colors[0] },
]);

function getRandomColor() {
  return colors[Math.floor(Math.random() * (colors.length - 0) + 0)];
}

function shuffleColors() {
  grid1.value.map((x) => (x.color = getRandomColor()));
  grid2.value.map((x) => (x.color = getRandomColor()));
}
</script>

<template>
  <div class="wrapper">
    <section class="px-10 py-10 h-full">
      <Grid>
        <template v-for="blox in grid1">
          <Blox :color="blox.color" :css="blox.id" @clicked="shuffleColors">
            <b>{{ blox.id }}</b>
          </Blox>
        </template>
      </Grid>
    </section>
    <section class="px-10 pb-10 h-full">
      <Grid>
        <template v-for="blox in grid2">
          <Blox :color="blox.color" :css="blox.id" @clicked="shuffleColors">
            <b>{{ blox.id }}</b>
          </Blox>
        </template>
      </Grid>
    </section>
  </div>
</template>

<style scoped>
@import './demo.css';
@import './colors.css';

.wrapper {
  display: flex;
  flex-direction: column;

  height: 100vh;
}

/* padding: util classes */

.pb-10 {
  padding-bottom: 10px;
}

.px-10 {
  padding-left: 10px;
  padding-right: 10px;
}

.py-10 {
  padding-top: 10px;
  padding-bottom: 10px;
}

/* height: util class */

.h-full {
  height: 100%;
}
</style>
