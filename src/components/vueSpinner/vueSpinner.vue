<script setup>
</script>

<template>
  <div class="spinner-container">
    <div class="spinner"></div>
  </div>
</template>


<style scoped>
.spinner-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.spinner {
  width: 32px;
  height: 32px;
  border: 4px solid #333;
  border-top-color: transparent;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}
</style>
