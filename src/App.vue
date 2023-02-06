<script setup lang="ts">
  import Modal from "./components/Modal/Modal.vue";
  import Search from "./components/Search/Search.vue";
  import Tab from "./components/Tab/Tab.vue";
</script>

<template>
  <h1>Vue課題</h1>
  <section>
    <h2>タブ</h2>
    <Tab />
  </section>
  <section>
    <h2>モーダルウィンドウ</h2>
    <Modal />
  </section>
  <section>
    <h2>リアルタイム検索</h2>
    <Search />
  </section>
</template>

<style></style>
