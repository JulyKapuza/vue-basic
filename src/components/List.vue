<script setup>
import { ref } from 'vue'

let id = 0

const newTodo = ref('')
const todos = ref([
    { id: id++, text: 'Вивчити HTML' },
    { id: id++, text: 'Вивчити JavaScript' },
    { id: id++, text: 'Вивчити Vue' }
])

function addTodo() {
    todos.value.push({ id: todos.value.lenght + 1, text: newTodo.value   })
    newTodo.value = ''
}

function removeTodo(todo) {
    todos.value = todos.value.filter((item) => item !== todo)
   
}
</script>

<template>
    <div>
    <form @submit.prevent="addTodo">
            <input v-model="newTodo">
            <button>Додати завдання</button>
        </form>
        <ul>
            <li v-for="todo in todos" :key="todo.id">
                {{ todo.text }}
                <button @click="removeTodo(todo)">X</button>
            </li>
        </ul>
    </div>
    
</template>