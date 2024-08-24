<script>
import { ref } from "vue";

export default {
  setup() {
    const message = ref("Hello");
    const quantity = ref(1);

    const increment = () => quantity.value++
    const decrement = () => quantity.value--

    return {
      message,
      quantity,
      increment,
      decrement
    };
  },
};
</script>

<template>
  <h1>{{ message }}</h1>
  <p>Quantity: {{ quantity }}</p>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
  <input type="text" v-model="message" />
</template>

<style scoped></style>
