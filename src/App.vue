<script setup>
import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operacao = ref('soma');

const resultado = computed(() => {
  switch (operacao.value) {
    case 'soma':
      return num1.value + num2.value;
    case 'subtracao':
      return num1.value - num2.value;
    case 'multiplicacao':
      return num1.value * num2.value;
    case 'divisao':
      return num1.value / num2.value;
    default:
      return 0;
  }
});
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input v-model.number="num1" type="number" placeholder="Número 1" />
      <input v-model.number="num2" type="number" placeholder="Número 2" />
      <select v-model="operacao">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
    </div>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<style scoped>
#app {
  text-align: center;
  margin-top: 50px;
}
</style>
