<template>
  <MainView v-if="isAuthenticated" />
  <LoginView v-else @login-success="handleLoginSuccess" />
</template>

<script setup>
import { ref } from 'vue'
import LoginView from './views/LoginView.vue'
import MainView from './views/MainView.vue'

const isAuthenticated = ref(false)

const handleLoginSuccess = () => {
  isAuthenticated.value = true
}
</script>
