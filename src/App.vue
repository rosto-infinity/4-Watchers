<template>
  
    <input type="text" v-model="page.title" />
    Temps écoulé : {{ time }}

<button @click="reset" style="margin-left: 2rem;">Reset</button>
  
</template>
<script setup>
import { ref, watch, watchEffect } from 'vue';
import { useTimer } from './composable/useTimer';

const page = ref({
  title: '',
});


const {time, reset} = useTimer();

// const options = { immediate: true };
// watch(()=>page.value.title, (newPage, oldPage) => {
//   document.title = `Hello | ${newPage}`;
// });
// console.log(page.value.title);

watchEffect (() => {
  document.title = `Hello | ${page.value.title}`;
});
</script>