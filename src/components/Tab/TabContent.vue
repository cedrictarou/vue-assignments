<template>
  <div class="tab-content">
    <div class="tab-content__item show" :key="currentId">
      {{ current.content }}
    </div>
  </div>
</template>

<script setup lang="ts">
  import type { Item } from "./Tab.vue";
  defineProps<{
    currentId: number;
    current: Item;
  }>();
</script>

<style scoped>
  .tab-content {
    height: 200px;
    border: 1px solid #000;
  }
  .tab-content__item {
    display: none;
    font-size: 40px;
  }
  .tab-content__item.show {
    display: block;
  }
</style>
