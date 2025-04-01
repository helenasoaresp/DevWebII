<script setup>
  import { reactive, computed } from 'vue';

  const professor = reactive({
    nome: 'Eduardo da Silva',
    disciplinas: [
      'Desenvolvimento Web II',
      'Desenvolvimento de Aplicativos para Dispositivos Móveis' ,
    ],
  });

  const possuiDisciplinas = computed(() => {
    return professor.disciplinas.length > 0;
  })
</script>

<template>

  <div>
    <h1>Professor</h1>
    <p>Nome: {{ professor.nome }}</p>
    <p v-if="!possuiDisciplinas">O professor não possui disciplinas.</p>
    
    <div v-else>
      <p>O professor possui disciplinas.</p>
    </div>

    <ul>
        <li v-for="disciplina in professor.disciplinas" :key="disciplina">
          {{ disciplina }}
        </li>
      </ul>
  </div>

</template>

<style scoped>

</style>
