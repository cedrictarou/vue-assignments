<template>
  <div>
    <input
      type="button"
      id="openBtn"
      value="開く"
      class="openBtn"
      @click="openModal"
    />
    <ModalWindow :isOpen="isOpen" @closeModal="closeModal">
      <h2 class="title">title</h2>
      <p class="text">text</p>
    </ModalWindow>
  </div>
</template>

<script setup lang="ts">
  import { ref } from "vue";
  import ModalWindow from "./ModalWindow.vue";

  const isOpen = ref(false);
  const openModal = () => {
    isOpen.value = true;
  };
  const closeModal = () => {
    isOpen.value = false;
  };
</script>

<style scoped>
  .openBtn {
    display: block;
    margin: 50px auto;
  }
  .title,
  .text {
    color: #000;
  }
</style>
