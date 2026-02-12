<template>
  <main class="login-page d-flex align-items-center justify-content-center px-3 py-5">
    <section class="login-card shadow-lg">
      <div class="text-center mb-4">
        <img src="../assets/img.jpg" alt="Logo Bem-Estar" class="logo mb-3" />
        <h1 class="h3 fw-bold mb-1">Entrar</h1>
        <p class="text-muted mb-0">Acesse sua conta para continuar.</p>
      </div>

      <form @submit.prevent="handleSubmit" novalidate>
        <div class="mb-3">
          <label for="email" class="form-label fw-semibold">E-mail</label>
          <input
            id="email"
            v-model.trim="form.email"
            type="email"
            class="form-control form-control-lg"
            placeholder="seuemail@exemplo.com"
            :class="{ 'is-invalid': errors.email }"
          />
          <p v-if="errors.email" class="invalid-feedback d-block mb-0">{{ errors.email }}</p>
        </div>

        <div class="mb-2">
          <label for="password" class="form-label fw-semibold">Senha</label>
          <input
            id="password"
            v-model="form.password"
            :type="showPassword ? 'text' : 'password'"
            class="form-control form-control-lg"
            placeholder="Digite sua senha"
            :class="{ 'is-invalid': errors.password }"
          />
          <p v-if="errors.password" class="invalid-feedback d-block mb-0">{{ errors.password }}</p>
        </div>

        <div class="d-flex justify-content-between align-items-center mb-4 mt-2">
          <div class="form-check">
            <input id="showPassword" v-model="showPassword" class="form-check-input" type="checkbox" />
            <label class="form-check-label" for="showPassword">Mostrar senha</label>
          </div>
          <a href="#" class="small text-decoration-none">Esqueci minha senha</a>
        </div>

        <button type="submit" class="btn btn-primary btn-lg w-100">Entrar</button>
      </form>

      <div
        v-if="status.message"
        class="alert mt-4 mb-0"
        :class="status.type === 'success' ? 'alert-success' : 'alert-danger'"
      >
        {{ status.message }}
      </div>
    </section>
  </main>
</template>

<script setup>
import { reactive, ref } from 'vue'

const emit = defineEmits(['login-success'])

const form = reactive({
  email: '',
  password: ''
})

const errors = reactive({
  email: '',
  password: ''
})

const status = reactive({
  type: '',
  message: ''
})

const showPassword = ref(false)

const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/

const clearFeedback = () => {
  errors.email = ''
  errors.password = ''
  status.type = ''
  status.message = ''
}

const validateForm = () => {
  let isValid = true

  if (!form.email) {
    errors.email = 'Informe seu e-mail.'
    isValid = false
  } else if (!emailRegex.test(form.email)) {
    errors.email = 'Digite um e-mail válido.'
    isValid = false
  }

  if (!form.password) {
    errors.password = 'Informe sua senha.'
    isValid = false
  } else if (form.password.length < 6) {
    errors.password = 'A senha deve ter pelo menos 6 caracteres.'
    isValid = false
  }

  return isValid
}

const handleSubmit = () => {
  clearFeedback()

  if (!validateForm()) {
    status.type = 'error'
    status.message = 'Corrija os campos obrigatórios.'
    return
  }

  status.type = 'success'
  status.message = 'Login validado no front-end com sucesso!'

  emit('login-success')
}
</script>

<style scoped>
.login-page {
  min-height: 100vh;
  background: linear-gradient(145deg, #eef2ff 0%, #ecfeff 100%);
}

.login-card {
  width: min(100%, 460px);
  background-color: #ffffff;
  border-radius: 18px;
  padding: 2rem;
  border: 1px solid rgba(15, 23, 42, 0.08);
}

.logo {
  width: 74px;
  height: 74px;
  border-radius: 18px;
  object-fit: cover;
  box-shadow: 0 8px 22px rgba(15, 23, 42, 0.2);
}

.form-control,
.btn {
  border-radius: 12px;
}
</style>
