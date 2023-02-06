<template>
  <div class="tab-menu">
    <input
      class="tab-menu__item"
      v-for="item in items"
      :class="currentId === item.id && 'active'"
      @click="switchTab(item.id)"
      :key="item.id"
      :value="item.label"
    />
  </div>
</template>

<script setup lang="ts">
  import type { Item } from "./Tab.vue";
  defineProps<{
    items: Item[];
    currentId: number;
  }>();

  const emit = defineEmits<{
    (event: "switchTab", id: number): void;
  }>();
  const switchTab = (id: number): void => {
    emit("switchTab", id);
  };
</script>

<style scoped>
  .tab-menu {
    display: flex;
  }
  .tab-menu__item {
    text-align: center;
    padding: 10px 0;
    cursor: pointer;
    list-style: none;
    width: 100px;
    border-top: 1px solid #000;
    border-left: 1px solid #000;
    border-right: 1px solid #000;
  }
  .tab-menu__item:not(:first-child) {
    border-left: none;
  }
  .tab-menu__item.active {
    background: #000;
    color: white;
  }
</style>
