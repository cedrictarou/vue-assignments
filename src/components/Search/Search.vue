<template>
  <div>
    <input type="text" v-model="keyword" />
    <SearchResult :filtered-items="filteredItems" />
  </div>
</template>

<script setup lang="ts">
  import { reactive, ref, computed } from "vue";
  import SearchResult from "./SearchResult.vue";

  export type Item = {
    id: number;
    name: string;
  };
  const keyword = ref<string>("");
  const items = reactive<Item[]>([
    {
      id: 1,
      name: "山田",
    },
    {
      id: 2,
      name: "斎藤",
    },
    {
      id: 3,
      name: "鈴木",
    },
    {
      id: 4,
      name: "田中",
    },
  ]);
  const filteredItems = computed(() => {
    const filteredItems = reactive<Item[]>([]);
    items.forEach((item): void => {
      if (item.name.indexOf(keyword.value) !== -1) {
        filteredItems.push(item);
      }
    });
    return filteredItems;
  });
</script>

<style scoped></style>
