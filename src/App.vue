<template>
  <div>
    <p>First: {{ first }}</p>
    <p>Squad of first: {{ firstSqaud }}</p>
    <button @click="add">add</button>

    <p>Second: {{ second }}</p>
    <button @click="addSecond">add to second</button>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const first = ref(1);
const second = ref(1);

const add = () => first.value++;
const addSecond = () => second.value++;

const firstSqaud = computed(() => {
  console.log('Была вызвана фукнция firstSquad');
  return first.value * first.value;
});
</script>

<style scoped></style>
