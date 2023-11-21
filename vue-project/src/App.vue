<script setup>
  import { ref, computed } from 'vue'
  const cursos = ref([])
  const hora = ref([])
  const curso = ref()
  const horas = ref()
  const mensaje = ref()

 

  const guardar = ()=>{
    curso.value && horas.value  ? (cursos.value.push(curso.value))&&(hora.value.push(horas.value)): alert("faltan datos");
    curso.value=""
    horas.value=""
    
  };
  
</script> 

<template>
  <h1>mis cursos</h1>
  <div>
    <input type="text" placeholder="curso" v-model="curso">
    <input type="text" placeholder="Horas" v-model="horas">
    <button @click="guardar" @change="totalHOras">guardar cursos</button>
  </div>

  <ul>
    <h2>lista de cursos cursos</h2>
    <li v v-for="cur in cursos">{{ cur }}</li>
  </ul>
 
  <h1 v-if="hora.length==0">por ahora no tiene horas de estudio</h1>
  <h1 v-else> su total de horas en cursos son:{{ mensaje=(hora.reduce((a, b) => Number(a) + Number(b), 0)) }}</h1>
  
  
  

</template>

<style>

</style>
