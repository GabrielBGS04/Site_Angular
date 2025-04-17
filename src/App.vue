<template>
  <div style="text-align: center; padding: 20px">
    <h1>ClickMaster 3000</h1>
    <h2>{{ contador }}</h2>
    <button @click="incrementar">+1</button>
    <button @click="decrementar">-1</button>
    <button @click="resetar">Resetar</button>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const contador = ref(parseInt(localStorage.getItem('contador')) || 0);

watch(contador, (novo) => {
  localStorage.setItem('contador', novo);
});

const incrementar = () => contador.value++;
const decrementar = () => contador.value--;
const resetar = () => contador.value = 0;
</script>
