<template>
  <template v-if="isAuthenticated">
    <TheNavBar />
    <TheTemplate />
    <TheFooter />
  </template>

  <LoginView v-else @login-success="handleLoginSuccess" />
</template>

<script setup>
import { ref } from 'vue'
import TheFooter from './components/TheFooter.vue'
import TheNavBar from './components/TheNavBar.vue'
import LoginView from './views/LoginView.vue'
import TheTemplate from './views/TheTemplate.vue'

const isAuthenticated = ref(false)

const handleLoginSuccess = () => {
  isAuthenticated.value = true
}
</script>
