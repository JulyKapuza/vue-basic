<script setup>
import { reactive, ref } from "vue";

const counter = reactive({ count: 20 });
const msg = ref("Привіт, світе!");
const titleClass = ref("title");
const subtitleClass = ref("subtitle");
const isButtonDisabled = true;
</script>

<template>
  <div>
    <h1 :class="titleClass">{{ msg }}</h1>
    <p :class="subtitleClass">Рахунок: {{ counter.count }}</p>
    <button :disabled="isButtonDisabled">Bind</button>
  </div>
</template>

<style scoped>
.title {
  color: aqua;
}
.subtitle {
  color: cadetblue;
}
</style>
