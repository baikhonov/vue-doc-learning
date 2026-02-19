<script setup>
import { ref, reactive, computed } from 'vue';

const isActive = ref(true);
const activeClass = ref('active');
const errorClass = ref('text-danger');

const activeColor = ref('red');
const fontSize = ref(30);

const styleObject = reactive({
  color: 'green',
  fontSize: '24px',
});
</script>

<template>
  <div :style="styleObject">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui illum
    asperiores non excepturi tempore vero, aliquid nisi quidem soluta delectus
    nostrum expedita corporis ipsum harum ducimus nulla. Mollitia, libero
    distinctio!
  </div>
</template>

<style scoped>
.static {
  font-weight: bold;
}

.active {
  width: fit-content;
  padding: 10px;

  background: orange;
}

.text-danger {
  color: white;
  background: rgb(221, 4, 4);
}

.info {
  font-style: italic;
}
</style>
