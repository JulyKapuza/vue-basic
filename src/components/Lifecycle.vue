<script setup>
import { ref, onMounted } from 'vue'

const p = ref(null)

onMounted(() => {
    p.value.textContent = 'Змонтовано!'
})
</script>

<template>
    <p ref="p">Привіт</p>
</template>