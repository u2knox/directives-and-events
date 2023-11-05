<template>
  <div>
    <button @click="changeLanguage">Сменить язык</button>
    <button @click="changeType">Сменить тип</button>
    <input
      :type="type"
      :value="inputValue"
    />
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const language = ref<string>('ru');
const type = ref<string>('text');

const inputValue = computed<string>(() => {
  if (language.value == 'ru') {
    return 'На русском';
  } else {
    return 'Казакша';
  }
});

const changeLanguage = () => {
  if (language.value == 'ru') {
    language.value = 'kk';
  } else {
    language.value = 'ru';
  }
};

const changeType = () => {
  if (type.value == 'text') {
    type.value = 'password';
  } else {
    type.value = 'text';
  }
};
</script>

<style scoped></style>
