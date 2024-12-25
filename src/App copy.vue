<template>
  <fieldset>
    <div>
      <p>Valeur : {{ data }}</p>
      
      <button @click="increment">Incrémenter</button>
    </div>
  </fieldset>
  </template>
  
  <script setup>
  import {
    ref,
    watch,
    computed
  } from 'vue';
  
  const data = ref(0);
  const computedValue = computed(() => data.value * 2);
 
  watch(data, (newValue, oldValue) => {
    console.log(`La valeur de data est passée de ${oldValue} à ${newValue}`);
    
  }, {immediate: true});
  const increment = () => {
    data.value++;
  };
  </script>
  