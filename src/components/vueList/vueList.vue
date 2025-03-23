<script setup>
import vueUserItem from '../vueUserItem/vueUserItem.vue'

defineProps({
  users: Array,
})
</script>

<template>
  <vueUserItem v-for="user in users" :key="user.id" :user="user" />
</template>

<style scoped></style>
