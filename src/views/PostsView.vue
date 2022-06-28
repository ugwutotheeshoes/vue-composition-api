<template>
  <div class="posts">
    <h1>posts</h1>

    <ul>
      <li>
        <router-link to="/postDetail/1">Post 1</router-link>
      </li>
      <li>
        <router-link to="/postDetail/2">Post 2</router-link>
      </li>
      <li>
        <router-link to="/postDetail/3">Post 3</router-link>
      </li>
    </ul>
    <textarea v-autofocus cols="30" rows="10"></textarea>
  </div>
</template>

<script setup>
import { vAutofocus } from "../directives/vAutofocus";
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
