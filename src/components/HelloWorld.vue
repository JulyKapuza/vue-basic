<script setup>
import { ref } from "vue";

const msg = ref("Hello World!");
</script>

<template>
  <div>
    <h1>{{ msg || 'Welcome!' }}</h1>
    <h2>{{ msg.toLocaleUpperCase() }}</h2>
    <input v-model="msg" />
  </div>
</template>
