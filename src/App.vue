<!-- Устаревший способ объявлять реактивные переменные -->
<!-- <script>
import { ref } from "vue";

export default {
  setup() {
    const count = ref(0);

    return {
      count,
    };
  },
};
</script> -->

<!-- Cовременный способ -->
<script setup>
import { ref, reactive } from "vue";

// const count = ref(0);
// const state = reactive({
//   count,
// });

// console.log(state.count); // 0

// state.count = 1;
// console.log(count.value); // 1

// console.log("------------------");
// const otherCount = ref(2);

// state.count = otherCount;
// console.log(state.count); // 2
// // старая ref-ссылка теперь не влияет на state.count
// console.log(count.value); // 1

// const count = ref(0);
// const state = reactive({
//   count,
// });

// console.log(state.count);
// state.count = 1;
// console.log(count.value);

// const otherCount = ref(2);

// state.count = otherCount;
// console.log(state.count);
// console.log(count.value);

const books = reactive([ref("Vue 3 Guide")]);
console.log(books[0].value);

const map = reactive(new Map([["count", ref(0)]]));
console.log(map.get("count").value);
</script>

<template>
  <div></div>
</template>

<style scoped>
/* Базовые стили для элементов формы */
button {
  padding: 12px 24px;
  border: none;
  border-radius: 8px;
  background: #3b82f6;
  color: white;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
}

button:hover {
  background: #2563eb;
  transform: translateY(-1px);
}

button:active {
  transform: translateY(0);
}

button:disabled {
  background: #9ca3af;
  cursor: not-allowed;
  transform: none;
}

.btns {
  display: flex;
  justify-content: center;
  gap: 10px;
}

/* Вариации кнопок */
.btn-secondary {
  background: #6b7280;
}

.btn-secondary:hover {
  background: #4b5563;
}

.btn-success {
  background: #10b981;
}

.btn-success:hover {
  background: #059669;
}

.btn-danger {
  background: #ef4444;
}

.btn-danger:hover {
  background: #dc2626;
}

/* Поля ввода */
input,
select,
textarea {
  padding: 12px 16px;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.2s ease;
  width: 100%;
  box-sizing: border-box;
}

input:focus,
select:focus,
textarea:focus {
  outline: none;
  border-color: #3b82f6;
}

/* Карточки */
.card {
  background: white;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  border: 1px solid #f3f4f6;
}

/* Контейнеры */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Утилиты */
.text-center {
  text-align: center;
}
.mt-4 {
  margin-top: 24px;
}
.mb-4 {
  margin-bottom: 24px;
}
.p-4 {
  padding: 24px;
}
</style>
