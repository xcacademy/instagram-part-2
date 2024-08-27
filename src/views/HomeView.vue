<script setup>

import Navbar from '../components/Navbar.vue';
import Post from '../components/Post.vue';
import {reactive} from "vue";
import { onMounted } from "vue"


const posts = reactive([])

onMounted(() => {
  getPosts()
})

function getPosts() {
 
  fetch('https://66ccd18b8ca9aa6c8cc8cbc0.mockapi.io/post')
    .then(response => response.json())
    .then(json => {
      console.log(json)
        posts.value = json
        console.log(posts)
    })

  
}

</script>

<template>
  <Navbar></Navbar>
  <div class="flex-container">
  <Post v-for="post in posts.value" :post='post'></Post>
</div>  
</template>

<style scoped>
Navbar {
  width: 100%;
}

.flex-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
}


</style>
