<script setup>
defineProps({
  email: String,
  phone: String,
  isVisible: Boolean
});
</script>

<template>
  <transition name="fade" mode="out-in">
    <div v-if="isVisible" class="details">
      <p><b>Email:</b> {{ email }}</p>
      <p><b>Phone:</b> {{ phone }}</p>
    </div>
  </transition>
</template>

<style scoped>
.details {
  margin-top: 5px;
  padding: 10px;
  width: 100%;
  border-bottom: 1px solid #333;
  border-radius: 4px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
  background: #f4f4f4;
}

.fade-enter-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
