<script setup>
import { ref, computed } from 'vue'
//---1.IDENTIFICAO---
const name = ref('')

//---2.DADOS DA SOMA---
const number1 = ref(0)
const number2 = ref(0)
const resultadoSoma = computed(() => number1.value + number2.value)
//---DADOS DAS NOTAS (MEDIA)---
//-- Aqui é onde voce cria as "caixas" para as 4 notas
const nota1 = ref(0)
const nota2 = ref(0)
const nota3 = ref(0)
const nota4 = ref(0)

//--- A conta da media: soma as 4 e divide por  2--  
const mediaFinal = computed(() => {
  return (nota1.value + nota2.value + nota3.value + nota4.value) / 2
})

</script>

<template>
  <div class="main.container"></div>
  <h1> Aula de Lógica, SENAI</h1>
  <h1> Exercícios de Fixação - Nível 1</h1>
  <section class="exercício"></section>

  <section class="card">
    <h2> Identificação</h2>
    <input v-model="name" placeholder="Digite seu nome">
    <h3 v-if="name">Olá {{ name }}, Bem vindo ao curso de lógica! </h3>
  </section>

  <div v-if="name">
    <section class="card">


      <h2>Soma Simples</h2>
      <p>Digite dois números para somar</p>
      <input type="number" v-model.number="number1">
      <span> + </span>
      <input type="number" v-model.number="number2">

      <p v-if="number1 || number2">
        o resultado da soma é: <strong> {{ resultadoSoma }}</strong>
      </p>
    </section>

  </div>


  <section class="card">
    <h2>Média Aritmética</h2>
    <p>Insira as 4 notas do aluno abaixo:</p>

    <div class="notas-group">
      <input type="number" v-model.number="nota1" v-model="nota1" placeholder="nota 1">
      <input type="number" v-model.number="nota1" v-model="nota2" placeholder="nota 2">
      <input type="number" v-model.number="nota1" v-model="nota3" placeholder="nota 3">
      <input type="number" v-model.number="nota1" v-model="nota4" placeholder="nota 4">
    </div>
    <div class="resultado" v-if="nota1 || nota2 || nota3 || nota4">
      <p> A média das notas é <strong>{{ mediaFinal }}</strong></p>

      <p v-if="mediaFinal >= 7" style="color:green">Status: Aprovado!</p>
      <p v-else style="color:red">Reprovado</p>

    </div>
  </section>


</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
