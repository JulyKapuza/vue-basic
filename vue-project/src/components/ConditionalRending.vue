<script setup>
const num = 5;
const display = true;
const showEl = true;
</script>

<template>
  <div>
    <!-- якщо умова правдива відбувається рендеринг якщо num ===0 -->
    <h2 v-if="num === 0">The number is zero</h2>
    <h2 v-else-if="num < 0">The number is negative</h2>
    <h2 v-else-if="num > 0">The number is positive</h2>
    <!-- v-else має стояти після v-if   -->
    <h2 v-else>Not a number</h2>
    <!-- Щоб застосувати умову до декількох ел, огортаєм тегом div, але створюється додатковий вузол в DOM, для того, щоб цього не було використовуємо обгортку template -->
    <template v-if="display">
      <h3>Juliia</h3>
      <h3>Codevolution</h3>
      <h3>Vue</h3>
    </template>
<!-- якщо вказано showEl = false v-if елемент зовсім не присутній в дом, в з директивою v-show має властивінсть display none-->
    <h2 v-show="showEl">Using v-show</h2>
    <h2 v-if="showEl">Using v-if</h2>
  </div>
</template>

<style scoped></style>
