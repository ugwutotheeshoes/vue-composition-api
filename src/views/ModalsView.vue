<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <component v-if="showModal" :is="Modal" @hideModal="showModal = false">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorem fuga
        at nobis ducimus quaerat obcaecati iusto voluptates deleniti maiores
        libero cumque incidunt esse, veniam qui quisquam saepe error, recusandae
        delectus?
      </p>
    </component>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Modal from "../components/Modal.vue";

const showModal = ref(false);
</script>

<style>
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
  color: hsl(160, 100%, 37%);
  text-transform: uppercase;
}
.modal {
  background: rgb(218, 217, 217);
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}
</style>
