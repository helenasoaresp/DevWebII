<script setup>
  import { computed, ref } from 'vue';

  const contador1 = ref(0);
  const contador2 = ref(0);
  const booleano =  ref(true);

  function incrementar(contador) {
    eval(contador).value++
  }

  function decrementar(contador) {
    if (eval(contador).value > 0) {
      eval(contador).value--
    }
  }

  const soma = computed(() => contador1.value + contador2.value);
  const maiorQue10 = computed(() => soma.value > 10);
  const par = computed(() => soma.value % 2 == 0);

</script>

<template>
  
  <div class="booleano">
    <button @click="valorBooleano = !valorBooleano">
      {{ valorBooleano ? 'Esconder Resultado' : 'Mostrar Resultado' }}
      
    </button>
  </div>

  <div v-if="booleano">
    <div class="contador">
      <h2>Contador 1</h2>
      <button @click="incrementar('contador1')">Incrementar</button>
      <button @click="decrementar('contador1')">Decrementar</button>
      <p>Valor: {{ contador1 }}</p>
    </div>

    <div class="contador">
      <h2>Contador 2</h2>
      <button @click="incrementar('contador2')">Incrementar</button>
      <button @click="decrementar('contador2')">Decrementar</button>
      <p>Valor: {{ contador2 }}</p>
    </div>

    <div class="soma">
      <h2>Soma</h2>
      <p>Valor da soma: {{ soma }}</p>
    </div>

    <div v-if="maiorQue10">
      <p>Maior que 10</p>
    </div>
    <div v-else>
      <p>Menor que 10</p>
    </div>
  </div>

  <div v-if="par">
    <p>A soma é par</p>
  </div>
  <div v-else>
    <p>A soma é impar</p>

  </div>

</template>

<style scoped>

  h2 {
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    color: rgb(51, 53, 0);
  }

  p {
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }

  button {
    border: none;
    background-color: rgba(242, 255, 128, 0.411);
    border-radius: 5px;
    padding: 8px;
    margin: 3px;
  }

</style>
