<script setup>
import { ref, computed } from 'vue';

const items = ref([
  { id: 1, message: 'Hello Foo world' },
  { id: 2, message: 'Bar and baz' },
  { id: 3, message: 'Foo is great' },
  { id: 4, message: 'No match here' },
  { id: 5, message: 'foo (lowercase)' },
  { id: 6, message: 'Football' },
  { id: 7, message: 'Something Foo something' },
  { id: 8, message: 'Just text' },
]);

const showFiltered = ref(false);

const displayedItems = computed(() => {
  if (showFiltered.value) {
    return items.value.filter((item) => item.message.match(/Foo/));
  }
  return items.value;
});

function filterItems() {
  showFiltered.value = true;
}

function resetFilter() {
  showFiltered.value = false;
}
</script>

<template>
  <div>
    <p>Количество элементов: {{ displayedItems.length }}</p>
    <ul>
      <li v-for="item in displayedItems" :key="item.id">
        {{ item.message }}
      </li>
    </ul>

    <button @click="filterItems">Показать только с Foo</button>
    <button @click="resetFilter" style="margin-left: 10px">
      Сбросить фильтр
    </button>
  </div>
</template>
