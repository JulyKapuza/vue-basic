<script setup>
import { ref } from "vue";

// const header = ref("Shoping List App");
const items = [
  { id: 1, label: "10 party hats" },
  { id: 2, label: "2 board games" },
  { id: 3, label: "20 cupst" },
];

const newItem = ref("");
</script>

<template>
  <div>
    <!-- <h1>{{ header }}</h1> -->
    <form
      v-on:submit.prevent="items.push({ id: items.length + 1, label: newItem })"
    >
      <input v-model.trim="newItem" type="text" placeholder="Add an item" />
      <button>Save Items</button>
    </form>

    <ul>
      <li class="list" v-for="{ id, label } in items" :key="id">
        {{ label }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
.list {
  color: cadetblue;
}
</style>
