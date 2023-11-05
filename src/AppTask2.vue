<template>
  <div>
    <h1>{{ arr }}</h1>
    <h1>{{ squadArr }}</h1>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

const arr = ref([1, 2, 3, 5, 8, 13, 21, 34]);

const squadArr = computed<number[] | number>(() => {
  // const tempArr: number[] = [];

  const resultValue: number = arr.value.reduce((acc: number, value: number) => {
    console.log(acc, value);
    return value + acc;
  })
  return resultValue;

  // const tempArr: number[] = arr.value.map((value: number) => Math.pow(value, 2))

  // const tempArr: number[] = arr.value.filter((value: number, index: number) => {
  //   return index % 2 === 0;
  // })
  // const tempArr: number[] = arr.value.filter((value: number) => value % 2 === 0)

  // arr.value.forEach((value: number) => {
  //   tempArr.push(Math.pow(value, 2))
  // });

  // for(let i = 0; i < arr.value.length; i++) {
  //   tempArr.push(Math.pow(arr.value[i], 2))
  // }
  // return tempArr;
})
</script>

<style scoped>

</style>