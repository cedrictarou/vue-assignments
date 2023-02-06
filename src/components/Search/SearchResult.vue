<template>
  <div v-for="item in filteredItems" :key="item.id">{{ item.name }}</div>
</template>

<script setup lang="ts">
  import type { Item } from "./Search.vue";
  defineProps<{
    filteredItems: Item[];
  }>();
</script>

<style scoped></style>
