<script>
import { ref, reactive } from "vue";

export default {
  setup() {
    const message = ref("Hello");
    const quantity = ref(1);
    const item = reactive({
      name: "Product 1",
      price: 10.99,
    });

    const increment = () => quantity.value++;
    const decrement = () => quantity.value--;

    const swapProduct = () => {
      item.name = "Product A";
      item.price = 9.99;
    };

    return {
      message,
      quantity,
      increment,
      decrement,
      item,
      swapProduct,
    };
  },
};
</script>

<template>
  <h1>{{ item.name }} : {{ item.price }}</h1>
  <button @click="swapProduct">Swap Product</button>
  <p>Quantity: {{ quantity }}</p>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
  <input type="text" v-model="message" />
</template>

<style scoped></style>
