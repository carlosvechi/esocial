<template>
  <LoginView v-if="!isAuthenticated" @login-success="isAuthenticated = true" />
  <template v-else>
    <TheNavBar />
    <TheTemplate />
    <TheFooter />
  </template>
</template>

<script setup>
import { ref } from 'vue'
import TheFooter from './components/TheFooter.vue'
import TheNavBar from './components/TheNavBar.vue'
import LoginView from './views/LoginView.vue'
import TheTemplate from './views/TheTemplate.vue'

const isAuthenticated = ref(false)
</script>
