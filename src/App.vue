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
const rawHtml = "<b>Жирный текст</b>";
const dynamicId = ref(2);
const id = ref(5);
const isButtonDisabled = ref(true);
const seen = ref(true);
const url = ref("https://google.com");
const someDynamicExpression = "href";
const someDynamicEvent = "click";

const objectOFAttrs = {
  id: "container",
  class: "wrapper",
  style: "background-color: orange",
};

// functions that mutate state and trigger updates
function increment() {
  count.value++;
  dynamicId.value++;
}

function doSomething() {
  console.log("Ты кликнул по кнопке");
}

function obSubmit() {
  console.log("Отправили данные формы");
}

onMounted(() => {
  // console.log(`The initial count is ${count.value}.`);
});
</script>
<!-- Composition API END -->

<template>
  <button @click="increment">Count is: {{ count }}</button>
  <p>Using text interpolation: {{ rawHtml }}</p>
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>
  <!-- Attribute Bindings -->
  <!-- <div v-bind:id="dynamicId"></div> -->
  <!-- Shorthand variant of v-bind -->
  <div :id="dynamicId">Просто div</div>
  <!-- Same-name Shorthand -->
  <!-- Тоже самое что :id="id" -->
  <!-- Или v-bind:id -->
  <!-- this is a feature that is only available in Vue 3.4 and above -->
  <div :id>А это div с одноимённым аттрибутом</div>
  <!-- Boolean Attributes -->
  <button :disabled="isButtonDisabled">Button</button>
  <div v-bind="objectOFAttrs">div для демонстрации применения объекта с аттрибутами</div>
  <p v-if="seen">Now you see me</p>
  <a v-bind:href="url" target="_blank">Google</a>
  <p></p>
  <!-- <button v-on:click="doSomething">Click me</button> -->
  <!-- Сокращённый вариант v-on - @ -->
  <button @click="doSomething">Click me</button>
  <p></p>
  <!-- Dynamic Arguments -->
  <!-- <a v-bind:[someDynamicExpression]="url" target="_blank">Ещё одна ссылка</a> -->
  <!-- Или сокращённый вариант -->
  <a :[someDynamicExpression]="url" target="_blank">Ещё одна ссылка</a>
  <p></p>
  <!-- <button v-on:[someDynamicEvent]="doSomething">Click me</button> -->
  <!-- Сокращённый вариант v-on - @ -->
  <button @[someDynamicEvent]="doSomething">Click Me Again</button>
  <p></p>
  <form @submit.prevent="obSubmit">
    <input type="text" name="name" placeholder="Имя" />
    <button type="submit">Send</button>
  </form>
</template>
