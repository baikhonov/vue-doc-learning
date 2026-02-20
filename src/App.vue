<script setup>
import { ref, reactive, computed } from 'vue';

const awesome = ref(true);
const type = ref('D');
const always = ref(true);
const ok = ref(false);
</script>

<template>
  <div>
    <button @click="awesome = !awesome">Переключить</button>
    <h1 v-if="awesome">Vue прекрасен! ❤️</h1>
    <h1 v-else>Vue ужасен! 😢</h1>

    <div v-if="type === 'A'">A</div>
    <div v-else-if="type === 'B'">B</div>
    <div v-else-if="type === 'C'">C</div>
    <div v-else>Точно не A, B или C</div>

    <template v-if="always">
      <h2>Несколько фактов о Сабине:</h2>
      <ul>
        <li>любит красные розы</li>
        <li>размер футболки 44, но хочет 52</li>
        <li>обожает косметику</li>
      </ul>
    </template>

    <h1 v-show="ok">Привет!</h1>
  </div>
</template>

<style scoped></style>
