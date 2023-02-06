<template>
  <div id="modal" class="modal" :class="{ open: isOpen }">
    <div class="modal__content" @click.self="closeModal">
      <div class="modal__content-inner">
        <slot></slot>

        <input type="button" id="closeBtn" value="閉じる" @click="closeModal" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  defineProps<{
    isOpen: boolean;
  }>();

  const emit = defineEmits<{
    (emit: "closeModal"): void;
  }>();

  const closeModal = () => {
    emit("closeModal");
  };
</script>

<style scoped>
  .modal.open {
    display: block;
    position: fixed;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.5);
  }
  .modal {
    display: none;
  }
  .modal__content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  .modal__content-inner {
    background-color: white;
    width: 500px;
    text-align: center;
    padding: 50px;
  }
</style>
