<script>
import { computed, ref, reactive, toRef, toRefs } from "vue";

export default {
  setup() {
    const item = reactive({
      name: "Product 1",
      price: 10.99,
      quantity: 1,
    });

    const increment = () => item.quantity++;
    const decrement = () => item.quantity--;

    const swapProduct = () => {
      item.name = "Product A";
      item.price = 9.99;
    };

    const total = computed(() => item.price * item.quantity);

    const { name, price, quantity } = toRefs(item);

    return {
      quantity,
      increment,
      decrement,
      item,
      name,
      price,
      total,
      swapProduct,
    };
  },
};
</script>

<template>
  <h1>{{ name }} : {{ price }}</h1>
  <button @click="swapProduct">Swap Product</button>
  <button @click="price++">Increment Price</button>
  <p>Quantity: {{ quantity }}</p>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
  <p>Total: {{ total }}</p>
</template>

<style scoped></style>
