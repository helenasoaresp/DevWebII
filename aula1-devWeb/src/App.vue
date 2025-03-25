<script setup>
  import { ref } from 'vue';
  const valor = ref(10);

  const temperatura_celsius = ref(0);
  const temperatura_farhenheit = ref(0);

  function converter_farhenheit() {
    temperatura_farhenheit.value = (temperatura_celsius.value * 9) / 5 + 32;
  }

  function decrementar() {
    valor.value--;
  }

  function duplicar() {
    valor.value = valor.value * 2;
  }

</script>

<template>

  <h1>Olá mundo!</h1>
  <button v-on:click="valor++">Incrementar</button>
  <button v-on:click="decrementar"> Decrementar</button>

  <button v-on:click="duplicar">Duplicar</button>

  <p>Valor: {{ valor }}</p>

  <hr>

  <input v-model="temperatura_celsius" type="number" step="0.1" />
  <button v-on:click="converter_farhenheit">Converter</button>
  <p>Temperatura em Fahrenheit: {{ temperatura_farhenheit }}</p>

</template>

<style scoped>

  button {
    font-weight: bold;
  }

</style>
