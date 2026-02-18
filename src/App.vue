<script setup>
import { ref, computed } from 'vue';

const count = ref(2);

const alwaysSmall = computed({
  get(previous) {
    if (count.value <= 3) {
      return count.value;
    }

    return previous;
  },
  set(newValue) {
    count.value = newValue * 2;
  },
});
</script>

<template>
  <div>{{ alwaysSmall }}</div>
</template>

<style scoped></style>
