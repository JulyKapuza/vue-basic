<script setup>
import { ref } from "vue";

const count = ref(0);
function increment() {
  count.value++;
}
</script>

<template>
  <!-- скорочений запис v-on:click="increment" -->
  <button class="btn" @click="increment">Рахунок: {{ count }}</button>
</template>

<style scoped>
.btn {
  background-color: aqua;
  color: cadetblue;
  width: 100px;
  height: 50px;
  border-radius: 5px;
}
</style>
