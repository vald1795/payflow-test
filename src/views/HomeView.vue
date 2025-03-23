<script setup>
import { ref, onMounted } from "vue";
import vueList from '../components/vueList/vueList.vue'
import vueSpinner from '../components/vueSpinner/vueSpinner.vue'


const users = ref([]);
const isLoading = ref(true);

const fetchUsers = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    users.value = await response.json();

    setTimeout(() => {
      isLoading.value = false;
    }, 1000);
  } catch (error) {
    console.error("Loading error...", error);
  }
};

onMounted(fetchUsers);
</script>

<template>
  <div class="list-container">
    <h2 class="list-header">USERS LIST</h2>
    <vueSpinner v-if="isLoading" />
    <vueList v-else :users="users" />
  </div>
</template>

<style scoped>
.list-container {
  padding: 20px;
  padding-bottom: 51px;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.list-header {
  margin-bottom: 10px;
  text-align: center;
}
</style>
