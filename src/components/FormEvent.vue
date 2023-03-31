<script setup>
import { ref } from "vue";

const header = ref("Shoping List App");
const items = ref([
  { id: 1, label: "10 party hats" },
  { id: 2, label: "2 board games" },
  { id: 3, label: "20 cups" },
]);

const newItem = ref("");

function addItem() {
  if (newItem.value !== "") {
    items.value.push({ id: items.value.length + 1, label: newItem.value });
    newItem.value = "";
  }
}
</script>

<template>
  <div>
    <h1>{{ header }}</h1>
    <form
     @submit.prevent="addItem" 
    >
      <input v-model.trim="newItem" type="text" placeholder="Add an item" />
      <button >Save Items</button>
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
