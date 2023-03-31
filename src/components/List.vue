<script setup>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
    { id: id++, text: 'Вивчити HTML', done: true },
    { id: id++, text: 'Вивчити JavaScript', done: true },
    { id: id++, text: 'Вивчити Vue', done: false }
])

const filteredTodos = computed(() => {
    return hideCompleted.value
        ? todos.value.filter((todo) => !todo.done)
        : todos.value
})

function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value })
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
            <li v-for="todo in filteredTodos" :key="todo.id">
                <input type="checkbox" v-model="todo.done">
                {{ todo.text }}
                <button @click="removeTodo(todo)">X</button>
            </li>
        </ul>
        <button @click="hideCompleted = !hideCompleted">
            {{ hideCompleted ? 'Показати всі' : 'Сховати виконані' }}
        </button>
    </div>
</template>