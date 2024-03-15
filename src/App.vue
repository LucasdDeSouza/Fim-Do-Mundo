<script setup>
import { computed, ref } from 'vue'

const listaCidade = ref(``)
const listaCidades = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília'
])

const Ordem = computed(() => [...listaCidades.value].sort())

function remover(index) {
  listaCidades.value.splice(index, 1)
}

function adicionar() {
  listaCidades.value.push(listaCidade.value)
  listaCidade.value = ''
}
</script>

<template>
  <h2>Formulário</h2>
  <div>
    <input type="text" v-model="listaCidade" />
    <button @click="adicionar">Adicionar</button>
  </div>
  <div class="resul">
    <div class="cid">
      <h2>Lista de cidades</h2>
      <ul>
        <li v-for="(listaCidade, index) in listaCidades" :key="index">
          {{ listaCidade }}
          <button @click="remover(index)">Remover</button>
        </li>
      </ul>
    </div>
  </div>
  <div class="cidades">
    <h2>Cidades ordenadas</h2>
    <ul>
      <li v-for="listaCidade in Ordem" :key="listaCidade">
        {{ listaCidade }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
