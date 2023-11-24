<script setup>
import { reactive } from 'vue';



const estado = reactive ({
  operacao: '',
  numeroA: 0,
  numeroB: 0,
})

const calculaNumeros = (a, b) => {
  a = Number(a);
  b = Number(b);

  const {operacao} = estado;
  switch(operacao){
    case '+':
      return a + b;
    case '-':
      return a - b;
    case '*':
      return a * b;
    case '/':
      return a / b;
    default:
      return '';  
  }
}



</script>

<template>

  <input :value="estado.numeroA" @keyup="event => estado.numeroA = event.target.value" type="number">
  <input :value="estado.numeroB" @keyup="event => estado.numeroB = event.target.value" type="number">
  <select @change="evento => estado.operacao = evento.target.value">
    <option>Escolha a operação</option>
    <option>+</option>
    <option>-</option>
    <option>*</option>
    <option>/</option>
  </select>
  <span>{{ calculaNumeros(estado.numeroA, estado.numeroB) }}</span>

</template>

<style scoped>

</style>
