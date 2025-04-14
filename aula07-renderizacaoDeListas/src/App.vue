<script setup>
import { computed, ref } from 'vue'

const cidade = ref('')
const cidades = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília',
])

const cidadesOrdenadas = computed(() => [...cidades.value].sort())

function adicionarCidade() {
  cidades.value.push(cidade.value)
  cidade.value = ''
}

function removerCidade(index) {
  cidades.value.slice(index, 1);
}

</script>

<template>
  <div class="correcao">
    <h1>Correção dos exercícios</h1>
    <div class="form">
      <input type="text" v-model="cidade" />
      <button @click="adicionarCidade">Adicionar</button>
    </div>
    <div class="resultados">
      <div class="cidades">
        <h2>Lista de cidades</h2>
        <ul>
          <li v-for="(cidade, index) in cidades" :key="index">
            {{ cidade }}
            <button @click="removerCidade(index)">Remover</button>
          </li>
        </ul>
      </div>
      <div class="cidades">
        <h2>Cidades ordenadas</h2>
        <ul>
          <li v-for="cidade in cidadesOrdenadas" :key="cidade">
            {{ cidade }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
