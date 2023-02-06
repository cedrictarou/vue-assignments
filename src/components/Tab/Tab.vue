<template>
  <div>
    <div class="tab">
      <TabLabel :items="items" :currentId="currentId" @switchTab="switchTab" />
      <TabContent :currentId="currentId" :current="current" />
    </div>
  </div>
</template>

<script setup lang="ts">
  import { computed, reactive, ref } from "vue";
  import TabLabel from "./TabLabel.vue";
  import TabContent from "./TabContent.vue";

  export type Item = {
    id: number;
    label: string;
    content: string;
  };

  const items: Item[] = reactive([
    {
      id: 1,
      label: "Tab1",
      content: "コンテンツ１",
    },
    {
      id: 2,
      label: "Tab2",
      content: "コンテンツ2",
    },
    {
      id: 3,
      label: "Tab3",
      content: "コンテンツ3",
    },
  ]);

  const currentId = ref<number>(1);
  const current = computed(() => {
    return items.find((el: Item) => el.id === currentId.value)!;
  });
  const switchTab = (id: number) => {
    currentId.value = id;
  };
</script>

<style scoped>
  .tab {
    width: 500px;
  }
</style>
