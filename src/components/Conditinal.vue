<script setup>
import { ref } from "vue";
const awesome = ref(true)
function toggle() {
    awesome.value = !awesome.value
}
</script>

<template>
    <div>
        <button @click="toggle">Change</button>
        <h1 v-if="awesome"> It's great 😊 </h1>
        <h1 v-else> Oooo nooo 😭 </h1>
    </div>
</template>