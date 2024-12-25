<template>
<fieldset>
  <div>
    <p>Valeur : {{ data }}</p>
    <p>la valeur calculéé  {{ computedValue }}</p>
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
watch(computedValue, (newValue, oldValue) => {
  console.log(`La valeur de data est passée de ${oldValue} à ${newValue}`);
  console.log(`La valeur calculée est passée de ${oldValue} à ${newValue} `);
});
const increment = () => {
  data.value++;
};
</script>
