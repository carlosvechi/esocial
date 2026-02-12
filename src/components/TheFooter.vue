<template>
  <footer v-if="isAuthenticated" class="mental-footer">
    <div class="container py-4">
      <div class="footer-box d-flex flex-column flex-md-row justify-content-between align-items-start align-items-md-center gap-3">
        <div class="d-flex align-items-center gap-3">
          <img src="../assets/img.jpg" alt="Logo" class="footer-logo" />
          <div>
            <div class="footer-title">Bem-Estar</div>
            <small class="footer-muted">Informação, acolhimento e consciência sobre saúde mental.</small>
          </div>
        </div>
        <div class="footer-quote text-md-end"><span>“Cuidar da mente é um ato de coragem.”</span></div>
      </div>

      <div class="footer-bottom d-flex flex-column flex-md-row justify-content-between align-items-center gap-2 mt-3">
        <small class="footer-muted">© {{ new Date().getFullYear() }} Bem-Estar • Projeto Educativo</small>
        <a class="back-top" href="#topo">Voltar ao topo ↑</a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const isAuthenticated = ref(false)

const updateAuth = () => {
  isAuthenticated.value = localStorage.getItem('isAuthenticated') === 'true'
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
.mental-footer { background: rgba(24, 32, 54, 0.92); backdrop-filter: blur(10px); border-top: 1px solid rgba(255, 255, 255, 0.08); color: rgba(255, 255, 255, 0.85); }
.footer-box { border: 1px solid rgba(255, 255, 255, 0.10); background: rgba(255, 255, 255, 0.05); border-radius: 16px; padding: 14px 16px; }
.footer-logo { height: 42px; width: 42px; border-radius: 14px; object-fit: cover; box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25); }
.footer-title { font-weight: 800; letter-spacing: 0.3px; line-height: 1.1; }
.footer-muted { color: rgba(255, 255, 255, 0.62); }
.footer-quote { font-style: italic; color: rgba(255, 255, 255, 0.75); font-size: 0.95rem; }
.footer-bottom { opacity: 0.95; }
.back-top { text-decoration: none; color: rgba(255, 255, 255, 0.7); padding: 6px 10px; border-radius: 12px; transition: 0.18s ease; }
.back-top:hover { color: #fff; background: rgba(255, 255, 255, 0.08); }
</style>
