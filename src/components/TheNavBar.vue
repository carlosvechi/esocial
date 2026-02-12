<template>
  <nav v-if="isAuthenticated" class="navbar navbar-expand-lg navbar-dark mental-nav sticky-top">
    <div class="container">
      <a class="navbar-brand d-flex align-items-center gap-2" href="#topo">
        <img src="../assets/img.jpg" alt="Logo" class="logo" />
        <span class="brand-text d-none d-sm-inline">Bem-Estar</span>
      </a>

      <button
        class="navbar-toggler shadow-none border-0"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarMental"
        aria-controls="navbarMental"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarMental">
        <ul class="navbar-nav mx-auto ranchers-regular align-items-lg-center gap-lg-2 mt-3 mt-lg-0">
          <li class="nav-item"><a class="nav-link" href="#topo" @click="closeMobileMenu">Home</a></li>
          <li class="nav-item"><a class="nav-link" href="#prevencao" @click="closeMobileMenu">Prevenção</a></li>
          <li class="nav-item"><a class="nav-link" href="#autocuidado" @click="closeMobileMenu">Autocuidado</a></li>
          <li class="nav-item"><a class="nav-link" href="#apoio" @click="closeMobileMenu">Apoio</a></li>
          <li class="nav-item"><a class="nav-link" href="#estigma" @click="closeMobileMenu">Combate ao estigma</a></li>
        </ul>

        <div class="d-flex gap-2 ms-lg-auto pb-3 pb-lg-0">
          <a href="#ajuda" class="btn btn-cta w-100 w-lg-auto" @click="closeMobileMenu">Canais de Ajuda</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const isAuthenticated = ref(false)

const updateAuth = () => {
  isAuthenticated.value = localStorage.getItem('isAuthenticated') === 'true'
}

const closeMobileMenu = () => {
  const el = document.getElementById('navbarMental')
  if (!el) return
  if (el.classList.contains('show')) el.classList.remove('show')
}

onMounted(() => {
  updateAuth()
  window.addEventListener('auth-changed', updateAuth)
})

onUnmounted(() => {
  window.removeEventListener('auth-changed', updateAuth)
})
</script>

<style scoped>
.mental-nav {
  background: rgba(24, 32, 54, 0.82);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}
.logo { height: 44px; width: 44px; object-fit: cover; border-radius: 14px; box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25); }
.brand-text { font-size: 1.05rem; letter-spacing: 0.4px; opacity: 0.95; }
.nav-link { color: rgba(255, 255, 255, 0.9) !important; font-size: 1.05rem; padding: 10px 14px !important; border-radius: 12px; transition: 0.18s ease; }
.nav-link:hover { background: rgba(255, 255, 255, 0.08); color: #fff !important; }
.btn-cta { border-radius: 14px; padding: 10px 14px; font-weight: 700; color: #0b1020; background: linear-gradient(135deg, #a5b4fc, #67e8f9); border: 0; }
.ranchers-regular { font-family: "Ranchers", sans-serif; font-weight: 650; }
@media (min-width: 992px) { .w-lg-auto { width: auto !important; } }
</style>
