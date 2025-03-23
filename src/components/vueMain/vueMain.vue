<script setup>
import { RouterView } from 'vue-router'
import vueSidebar from '../vueSidebar/vueSidebar.vue'
</script>

<template>
  <main>
    <RouterView />
    <vueSidebar />
  </main>
</template>

<style scoped>
main {
  min-height: calc(100vh - 100px);
  display: flex;
  background: #fff;
}
</style>
