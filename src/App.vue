<template>
  <LoginView v-if="!isAuthenticated" @login-success="isAuthenticated = true" />
  <TheTemplate v-else />
</template>

<script setup>
import { ref } from 'vue'
import LoginView from './views/LoginView.vue'
import TheTemplate from './views/TheTemplate.vue'

const isAuthenticated = ref(false)
</script>
