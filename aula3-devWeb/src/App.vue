<script setup>
  import {ref} from 'vue'

  const contador = ref(0);

  function incrementar() {
    contador.value++
  }

  function decrementar() {
    contador.value--
  }

</script>

<template>
  <h1>Contador</h1>

  <p>Valor do contador: {{contador}} </p>
  <button @click="incrementar">+</button>
  <button @click="decrementar">-</button>

</template>

<style scoped>

</style>
