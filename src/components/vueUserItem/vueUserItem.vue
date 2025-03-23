<script setup>
import { ref } from "vue";
import vueUserDetails from '../vueUserDetails/vueUserDetails.vue'

defineProps({
  user: Object,
});

const showDetails = ref(false);

const toggleDetails = () => {
  showDetails.value = !showDetails.value;
};

</script>

<template>
  <div class="list-item">
    <p><strong>{{ user.name }}</strong></p>
    <button @click="toggleDetails(user.id)">
      {{ showDetails ? "Hide details" : "Show details" }}
    </button>
    <vueUserDetails :email="user.email" :phone="user.phone" :isVisible="showDetails" />
  </div>
</template>

<style scoped>
.list-item {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
  padding: 10px 0px;
}

.list-item p {
  margin-bottom: 5px;
}

button {
  margin-bottom: 10px;
  padding: 5px 10px;
  border: none;
  border-radius: 4px;
  color: #fff;
  background: #333;
  cursor: pointer;
}

button:hover {
  background: #555;
}
</style>
