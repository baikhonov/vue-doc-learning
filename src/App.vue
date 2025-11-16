<!-- Options API START -->
<!-- <script>
export default {
  data() {
    // Properties returned from data() become reactive state
    // and will be exposed on `this`
    return {
      count: 0,
    };
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be found as event handlers in templates
  methods: {
    increment() {
      this.count++;
    },
  },

  // Lifecycle hooks are called at different stages
  // of a component's lifecycle.
  // This function will be called when the component is mounted/
  mounted() {
    console.log(`The initial count is ${this.count}.`);
  },
};
</script> -->
<!-- Options API END -->

<!-- Composition API START -->
<script setup>
import { ref, onMounted } from "vue";

// reactive state
const count = ref(0);

// functions that mutate state and trigger updates
function increment() {
  count.value++;
}

onMounted(() => {
  console.log(`The initial count is ${count.value}.`);
});
</script>
<!-- Composition API END -->

<template>
  <button @click="increment">Count is: {{ count }}</button>
</template>
