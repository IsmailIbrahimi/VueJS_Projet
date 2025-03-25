<script setup lang="ts">
import { onMounted } from 'vue'
import { useUserStore } from './stores/userStore'
import Navbar from './components/Navbar.vue'

const userStore = useUserStore()

onMounted(() => {
  userStore.loadFromLocalStorage()
})
</script>

<template>
  <Navbar v-if="userStore.isLoggedIn()" />
  <router-view />
</template>

<style scoped>
</style>
