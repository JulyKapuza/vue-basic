<script setup>
import { ref, reactive } from "vue";

const post = reactive({
  newTitle: '',
  newText: '',
})

let id = 0
const posts = ref([
  {
    id: 1,
    title: "JavaScript",
    text: "JavaScript is a scripting language that enables you to create dynamically updating content, control multimedia, animate images, and pretty much everything else. (Okay, not everything, but it is amazing what you can achieve with a few lines of JavaScript code.)",
  },
  {
    id: 2,
    title: "HTML",
    text: "HTML is the markup language that we use to structure and give meaning to our web content, for example defining paragraphs, headings, and data tables, or embedding images and videos in the page.",
  },
  {
    id: 3,
    title: "CSS",
    text: "CSS is a language of style rules that we use to apply styling to our HTML content, for example setting background colors and fonts, and laying out our content in multiple columns.",
  },
]);

function addPost() {
    posts.value.push({ id: id++, title:  post.newTitle, text:  post.newText })
    post.newTitle = ''
    post.newText = ''
} 
</script>

<template>
  <div class="container">
   <form  @submit.prevent="addPost">
            <h2>Add posts</h2>
            <input v-model="post.newTitle" class="input" type="text" placeholder="enter name" />
            <input v-model="post.newText" class="input" type="text" placeholder="description" />
            <button class="btn">Create post</button>
          </form>

    <ul>
      <li class="post" v-for="post in posts" :key="post.id">
        <h2>{{ post.title }}</h2>
        <p>{{ post.text }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.container{
    padding:20px;
}
.post {
  padding: 15px;
  border: 2px solid lightseagreen;
  margin-top: 10px;
}
.input{
    width: 100%;
    border: 1px solid lightskyblue;
    padding: 10px;
    margin-top: 10px;
}
.btn{
    background-color: transparent;
    color:lightskyblue;
    border: 1px solid lightskyblue;
    border-radius: 5px;
    padding: 5px;
    margin-top: 10px;
}

</style>