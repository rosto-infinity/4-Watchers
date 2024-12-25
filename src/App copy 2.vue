<template>
  
    <input type="text" v-model="name" />
  
</template>
<script setup>
import { ref, watch } from 'vue';

const name = ref('');
const options = { immediate: true };
watch(name, (newValue, oldValue) => {
  document.title = `Hello | ${newValue}`;
},options);
</script>