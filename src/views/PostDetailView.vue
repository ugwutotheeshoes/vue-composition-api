<template>
  <div class="post-detail">
    <h1>This is a post page</h1>
    <p>display post of ID {{ $route.params.id }}</p>

    <div>
      <button @click="showPostID">Show Post ID</button>
    </div>
    <div>
      <button @click="goHome">Go Home</button>
    </div>
    <button>
      <router-link to="/posts">&lt; go back to posts</router-link>
    </button>
  </div>
</template>

<script setup>
import { useRoute, useRouter } from "vue-router";
const route = useRoute();
const router = useRouter();

const showPostID = () => {
  console.log("show post");
  alert(`The ID of this post is: ${route.params.id}`);
};

const goHome = () => {
  setTimeout(() => {
    router.push("/");
  }, 3000);
  //we can also use the name assigned to the home router
// const goHome = () => {
//   setTimeout(() => {
//     router.push({name: 'home'});
//   }, 3000);
};
</script>

<style scoped>
p {
  text-transform: uppercase;
}
button {
  background: hsla(160, 100%, 37%, 1);
  color: white;
  text-transform: uppercase;
  border: transparent;
  padding: 0.5rem;
  border-radius: 25px;
  margin-top: 0.3rem;
  cursor: pointer;
}

a {
  color: white;
  text-transform: uppercase;
}
</style>
