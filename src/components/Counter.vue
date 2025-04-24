<script setup>
import { useCounter } from "../store";

const counterStore = useCounter();

counterStore.$subscribe((mutation, state) => {
  console.log("mutation :", mutation);
  console.log("state :", state);
});

counterStore.$onAction((action) => {
  console.log("action :", action);
});

function logDoubled() {
  const doubled = counterStore.doubled;
}
</script>

<template>
  <div>
    <h1>Counter : {{ counterStore.counter }}</h1>
    <button @click="counterStore.increment()">Increment</button>
    <button @click="counterStore.reset()">Reset</button>
    <button @click="logDoubled">Log Doubled</button>
  </div>
</template>

<style scoped></style>
