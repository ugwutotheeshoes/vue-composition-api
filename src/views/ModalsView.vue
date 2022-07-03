<template>
  <div class="modals">
    <h1>Modals</h1>
    <button>Show modal</button>
    <div class="modal" v-if="showModal">
      <h1>This is a modal</h1>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorem fuga
        at nobis ducimus quaerat obcaecati iusto voluptates deleniti maiores
        libero cumque incidunt esse, veniam qui quisquam saepe error, recusandae
        delectus?
      </p>
      <button>Hide modal</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const showModal = ref(false);
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
