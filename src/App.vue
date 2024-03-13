<script setup>
import { ref } from 'vue';
const listaCidades = ref( ['São Paulo','Rio de Janeiro', 'Belo Horizonte','Salvador', 'Fortaleza',
  'Curitiba','Manaus', 'Recife','Porto Alegre','Brasília',] );

function remover(index) {
    listaCidades.value.splice(index, 1);
  }

  function adicionar() {
    listaCidades.value.push(NovaCidade.value)
    novaCidade.value = ''
  }

  
</script>

<template>

   <input type="text" v-model="NovaCidade">
  <button @click="adicionar">Adicionar</button>
  <ul>
    <li v-for="item in listaCidades">{{ item }}</li>
  </ul>

   <ul>
    <li v-for="(item, index) in listaCidades " :key="index"> {{ item }} 
      <button @click="remover(index)">Remover</button></li>
   </ul>
  
</template>

<style scoped>

button{
  background-color: aqua;

}
</style>
