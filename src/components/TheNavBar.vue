<template>
  <nav class="navbar navbar-expand-lg navbar-dark mental-nav sticky-top">
    <div class="container">
      <a class="navbar-brand d-flex align-items-center gap-2" href="#" @click.prevent="goTo('home')">
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
          <li class="nav-item">
            <a class="nav-link" :class="{ active: currentPage === 'home' }" href="#" @click.prevent="goTo('home')">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" :class="{ active: currentPage === 'formulario' }" href="#" @click.prevent="goTo('formulario')">Formulário</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" :class="{ active: currentPage === 'recursos' }" href="#" @click.prevent="goTo('recursos')">Plano semanal</a>
          </li>
        </ul>

        <div class="d-flex gap-2 ms-lg-auto pb-3 pb-lg-0">
          <a
            href="#"
            class="btn btn-cta w-100 w-lg-auto"
            @click.prevent="goTo('formulario')"
          >
            Canais de Ajuda
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
defineProps({
  currentPage: {
    type: String,
    default: 'home'
  }
})

const emit = defineEmits(['navigate'])

const closeMobileMenu = () => {
  const el = document.getElementById('navbarMental')
  if (!el) return

  if (el.classList.contains('show')) {
    el.classList.remove('show')
  }
}

const goTo = (page) => {
  emit('navigate', page)
  closeMobileMenu()
}
</script>

<style scoped>
.mental-nav {
  background: rgba(24, 32, 54, 0.82);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.logo {
  height: 44px;
  width: 44px;
  object-fit: cover;
  border-radius: 14px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
}

.brand-text {
  font-size: 1.05rem;
  letter-spacing: 0.4px;
  opacity: 0.95;
}

.nav-link {
  color: rgba(255, 255, 255, 0.9) !important;
  font-size: 1.05rem;
  padding: 10px 14px !important;
  border-radius: 12px;
  transition: 0.18s ease;
}

.nav-link:hover,
.nav-link.active {
  background: rgba(255, 255, 255, 0.08);
  color: #fff !important;
}

.btn-cta {
  border-radius: 14px;
  padding: 10px 14px;
  font-weight: 700;
  color: #0b1020;
  background: linear-gradient(135deg, #a5b4fc, #67e8f9);
  border: 0;
}

.ranchers-regular {
  font-family: 'Ranchers', sans-serif;
  font-weight: 650;
}

@media (min-width: 992px) {
  .w-lg-auto {
    width: auto !important;
  }
}
</style>
