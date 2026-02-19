<template>
  <LoginView v-if="!isAuthenticated" @login-success="isAuthenticated = true" />

  <template v-else>
    <TheNavBar :current-page="currentPage" @navigate="navigateTo" />

    <TheTemplate v-if="currentPage === 'home'" @navigate="navigateTo" />
    <FormularioApoioView v-else-if="currentPage === 'formulario'" />
    <RecursosView v-else-if="currentPage === 'recursos'" />

    <TheFooter />
  </template>
</template>

<script setup>
import { ref } from 'vue'

import TheFooter from './components/TheFooter.vue'
import TheNavBar from './components/TheNavBar.vue'

import LoginView from './views/LoginView.vue'
import TheTemplate from './views/TheTemplate.vue'
import FormularioApoioView from './views/FormularioApoioView.vue'
import RecursosView from './views/RecursosView.vue'

const isAuthenticated = ref(false)
const currentPage = ref('home')

const navigateTo = (page) => {
  currentPage.value = page

  if (page === 'home') {
    window.scrollTo({ top: 0, behavior: 'smooth' })
  }
}
</script>
