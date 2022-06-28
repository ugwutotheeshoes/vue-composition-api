<template>
  <div class="post-detail">
    <h1>This is a post page</h1>
    <p>display post of ID {{ $route.params.id }}</p>
    <button>
      <router-link to="/posts"> go back to posts</router-link>
    </button>
  </div>
</template>

<script setup></script>

<style scoped>
p {
  text-transform: uppercase;
}
button {
  background: hsla(160, 100%, 37%, 1);
  border: transparent;
  padding: 0.5rem;
  border-radius: 25px;
  margin-top: 0.3rem;
}

a {
  color: white;
  text-transform: uppercase;
}
</style>
