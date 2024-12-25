<template>
 <input type="text" v-model="name" />
</template>


  <script setup>
  import { ref } from 'vue';
  const name = ref('');
  </script>
