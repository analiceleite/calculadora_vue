<template>
  <div class="container">
    <Calculadora
      :num1="estado.num1"
      :num2="estado.num2"
      :operator="estado.operator"
      :result="estado.result"
      :calculate="calculate"
      @update:num1="estado.num1 = $event; calculate()"
      @update:num2="estado.num2 = $event; calculate()"
      @update:operator="estado.operator = $event; calculate()"
    />
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  operator: '+',
  result: 0,
});

const calculate = () => {
  const num1 = Number(estado.num1);
  const num2 = Number(estado.num2);

  switch (estado.operator) {
    case '+':
      estado.result = num1 + num2;
      break;
    case '-':
      estado.result = num1 - num2;
      break;
    case '*':
      estado.result = num1 * num2;
      break;
    case '/':
      estado.result = num1 / num2;
      break;
  }
};
</script>
