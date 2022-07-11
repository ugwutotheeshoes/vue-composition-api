<template>
  <teleport to="body">
    <div class="modal">
      <h1>This is a modal</h1>
      <slot />
      <button @click="handleButton">Hide modal</button>
      <p>The username is: {{ userData.username }}</p>
    </div>
  </teleport>
</template>
<script setup>
import { inject } from "vue";
// emits method
const emit = defineEmits(["hideModal"]);

// handle button click

const handleButton = () => {
  emit("hideModal");
};

const userData = inject("userData");
</script>

<style scoped>
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
