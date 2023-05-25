<template>
    <div>
<button @click="getPosts">Load Posts</button>
        <div v-for="post in posts" :key="post.id">
                <h3 style="color:aqua">{{ post.title }}</h3>
                <p>{{ post.body }}</p>
        </div>
    </div>
</template>


<script setup>
import { ref } from 'vue';
import axios from 'axios'

let posts = ref([])
const getPosts = () => {
    axios.get(` https://jsonplaceholder.typicode.com/posts`)
        .then((response) => {
            posts.value = response.data;
        console.log(posts)
        })
    .catch((error)=>console.log(error))
}

 
</script>