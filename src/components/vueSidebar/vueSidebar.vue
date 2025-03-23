<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";

const windowWidth = ref(window.innerWidth);
const isSidebarVisible = ref(true);
const isRendered = computed(() => windowWidth.value > 700);

const updateWidth = () => {
  windowWidth.value = window.innerWidth;
};

onMounted(() => {
  window.addEventListener("resize", updateWidth);
});

onUnmounted(() => {
  window.removeEventListener("resize", updateWidth);
});
</script>


<template>
  <transition name="sidebar-fade" @after-leave="isSidebarVisible = false">
    <aside v-if="isRendered" class="sidebar">
      <h2 class="sidebar-header">SIDEBAR</h2>
    </aside>
  </transition>
</template>


<style scoped>
.sidebar {
  width: 300px;
  padding: 20px;
  padding-bottom: 51px;
  border-left: 1px solid #ccc;
  background: #fff;
  box-shadow: -15px 0 15px rgba(51, 51, 51, 0.5);
}

.sidebar-header {
  font-size: 20px;
  text-align: center;
}

.sidebar-fade-enter-active {
  transition: opacity 0.25s linear;
}

.sidebar-fade-leave-active {
  transition: opacity 0.25s ease-out;
}

.sidebar-fade-leave-to,
.sidebar-fade-enter-from {
  opacity: 0;
}

.sidebar-fade-enter-to,
.sidebar-fade-leave-from {
  opacity: 1;
}
</style>
