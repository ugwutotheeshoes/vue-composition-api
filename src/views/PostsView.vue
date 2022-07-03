<template>
  <div class="posts">
    <h1>posts</h1>

    <ul>
      <li v-for="post in posts" :key="post.id">
        <router-link :to="`/postDetail/${post.id}`">{{ post.name }}</router-link>
      </li>
     
    </ul>
    <textarea v-autofocus cols="30" rows="10"></textarea>
  </div>
</template>

<script setup>
import { vAutofocus } from "../directives/vAutofocus";

//for v-for, to loop thru an array of data
import { ref } from 'vue'

const posts = ref([
  {
    id: 1,
    name: 'Post 1'
  },
  {
    id: 2,
    name: 'Post 2'
  },
  {
    id: 3,
    name: 'Post 3'
  },
])
</script>

<style scoped>
.posts {
  text-transform: uppercase;
}

ul {
  list-style-type: none;
}

li {
  margin: 0.5rem;
}
</style>
