<template>
  <div class="user">
    <p>{{ userData.user }}</p>
    <p>@{{ userData.username }}</p>
     </div>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/modals">Modals</RouterLink>
    <RouterLink to="/posts">Posts</RouterLink>
  </nav>

  <RouterView />
</template>

<script setup>
import { reactive, provide } from "vue";

const userData = reactive({
  user: "Ugwu",
  username: "ugwutotheeshoes",
});

provide("userData", userData);
</script>

<style>
@import "@/assets/base.css";

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

.user {
  color: hsla(160, 100%, 37%, 1);
  position: absolute;
  top: 0;
  right: 0;
  display: flex;
  flex-direction: column;
  /* align-items: center; */
  justify-content: center;
  text-transform: uppercase;
  /* text-align: center; */
}
</style>
