<script setup>
import { useCounter } from "../store";

const counterStore = useCounter();

counterStore.$subscribe((mutation, state) => {
  console.log("mutation :", mutation);
  console.log("state :", state);
});

function handleClick() {
  counterStore.counter++;
}

function handleReset() {
  counterStore.$patch({
    counter: 0,
  });
}
</script>

<template>
  <div>
    <h1>Counter : {{ counterStore.counter }}</h1>
    <button @click="handleClick">Increament</button>
    <button @click="handleReset">Reset</button>
  </div>
</template>

<style scoped></style>
