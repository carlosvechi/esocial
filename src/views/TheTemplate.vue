<template>
  <main v-if="!isAuthenticated" class="login-page d-flex align-items-center justify-content-center px-3 py-5">
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

  <template v-else>
    <!-- Topo (âncora para Home) -->
    <div id="topo"></div>

    <!-- Headline -->
    <div class="container mt-5">
      <div class="p-4 border-start border-4 border-primary">
        <h1 class="lora fw-bold text-start m-0">
          Cuidar da mente é cuidar da vida.<br />
          <span class="text-primary">Bem-estar emocional no dia a dia.</span>
        </h1>
        <p class="mt-3 mb-0 text-muted">
          Informação, autocuidado, apoio psicológico e combate ao estigma — tudo em um só lugar.
        </p>
      </div>
    </div>

    <!-- Carousel -->
    <div id="demo" class="carousel slide mt-5" data-bs-ride="carousel">
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#demo" data-bs-slide-to="0" class="active sb"></button>
        <button type="button" data-bs-target="#demo" data-bs-slide-to="1" class="sb"></button>
        <button type="button" data-bs-target="#demo" data-bs-slide-to="2" class="sb"></button>
      </div>

      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="../assets/cuidado.png" alt="Autocuidado" class="d-block w-100" />
          <div class="carousel-caption caption-bg">Autocuidado: pequenas práticas, grandes mudanças</div>
        </div>

        <div class="carousel-item">
          <img src="../assets/rotina.png" alt="Ansiedade e rotina" class="d-block w-100" />
          <div class="carousel-caption caption-bg">Prevenção da ansiedade: rotina, sono e limites</div>
        </div>

        <div class="carousel-item">
          <img src="../assets/apoio.png" alt="Apoio psicológico" class="d-block w-100" />
          <div class="carousel-caption caption-bg">Apoio psicológico: pedir ajuda é coragem</div>
        </div>
      </div>

      <button class="carousel-control-prev" type="button" data-bs-target="#demo" data-bs-slide="prev">
        <span class="carousel-control-prev-icon"></span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#demo" data-bs-slide="next">
        <span class="carousel-control-next-icon"></span>
      </button>
    </div>

    <section id="prevencao" class="container mt-5">
      <div class="p-4 rounded-4 border">
        <h3 class="lora mb-3">Prevenção da ansiedade e depressão</h3>
        <div class="row g-3">
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Rotina e sono</strong><p class="mb-0 text-muted">Dormir bem regula humor e energia. Tente manter horários mais consistentes (inclusive no fim de semana).</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Redução de estresse</strong><p class="mb-0 text-muted">Respiração, pausas e “limites” (falar não) ajudam a reduzir sobrecarga mental no dia a dia.</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Rede de apoio</strong><p class="mb-0 text-muted">Conversar com alguém de confiança já é um passo. Isolamento costuma piorar sintomas.</p></div></div>
        </div>
      </div>
    </section>

    <section id="autocuidado" class="container mt-5">
      <div class="p-4 rounded-4 border bg-light">
        <h3 class="lora mb-3">Autocuidado e bem-estar emocional</h3>
        <div class="row g-3">
          <div class="col-md-6"><div class="p-3 rounded-4 bg-white border h-100"><strong>Checklist simples (diário)</strong><ul class="mb-0 text-muted mt-2"><li>Beber água e comer algo decente</li><li>10–20 min de movimento (caminhar já vale)</li><li>Uma pausa sem tela</li><li>Uma coisa prazerosa (música, hobby, leitura)</li></ul></div></div>
          <div class="col-md-6"><div class="p-3 rounded-4 bg-white border h-100"><strong>Autocompaixão</strong><p class="mb-0 text-muted mt-2">Não é “ser fraco”. É reconhecer limites. Troque “eu não consigo” por “eu estou tentando e posso pedir ajuda”.</p></div></div>
        </div>
      </div>
    </section>

    <section id="apoio" class="container mt-5">
      <div class="p-4 rounded-4 border">
        <h3 class="lora mb-3">Apoio psicológico</h3>
        <div class="row g-3">
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Quando buscar ajuda?</strong><p class="mb-0 text-muted">Se sintomas persistirem por semanas, atrapalharem rotina, sono, trabalho ou estudos.</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Terapia</strong><p class="mb-0 text-muted">Ajuda a entender pensamentos, emoções e comportamentos. É um espaço seguro e sem julgamento.</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-light border h-100"><strong>Como apoiar alguém</strong><p class="mb-0 text-muted">Escute, valide sentimentos, evite “é só…” e ofereça ajuda prática (acompanhar, pesquisar serviços, etc.).</p></div></div>
        </div>
      </div>
    </section>

    <section id="estigma" class="container mt-5">
      <div class="p-4 rounded-4 border bg-light">
        <h3 class="lora mb-2">Combate ao estigma</h3>
        <p class="mb-3 text-muted">Transtornos mentais não são “fraqueza” nem “frescura”. Falar sobre isso com respeito salva vidas.</p>
        <div class="row g-3">
          <div class="col-md-4"><div class="p-3 rounded-4 bg-white border h-100"><strong>Use linguagem respeitosa</strong><p class="mb-0 text-muted">Evite piadas e rótulos. Foque na pessoa, não no diagnóstico.</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-white border h-100"><strong>Incentive busca de ajuda</strong><p class="mb-0 text-muted">Terapia e acompanhamento médico são formas de cuidado, não vergonha.</p></div></div>
          <div class="col-md-4"><div class="p-3 rounded-4 bg-white border h-100"><strong>Escute sem julgar</strong><p class="mb-0 text-muted">Às vezes a melhor ajuda é presença + escuta de verdade.</p></div></div>
        </div>
      </div>
    </section>

    <section id="ajuda" class="container mt-5 mb-5">
      <div class="p-4 rounded-4 border">
        <h3 class="lora mb-3">Canais de ajuda</h3>
        <p class="text-muted mb-3">Se você estiver em sofrimento intenso, procure ajuda imediatamente. Se for emergência, busque um serviço local.</p>
        <div class="row g-3">
          <div class="col-md-6"><div class="p-3 rounded-4 bg-light border h-100"><strong>CVV (Centro de Valorização da Vida)</strong><p class="mb-2 text-muted">Apoio emocional e prevenção do suicídio (atendimento 24h, dependendo do canal).</p><span class="badge text-bg-dark">Ligue 188</span></div></div>
          <div class="col-md-6"><div class="p-3 rounded-4 bg-light border h-100"><strong>Rede pública e profissionais</strong><p class="mb-0 text-muted">Procure UBS/serviços de saúde da sua cidade e, se possível, psicólogo(a) ou psiquiatra.</p></div></div>
        </div>
      </div>
    </section>
  </template>
</template>

<script>
export default {
  data() {
    return {
      isAuthenticated: false,
      showPassword: false,
      form: { email: '', password: '' },
      errors: { email: '', password: '' },
      status: { type: '', message: '' }
    }
  },
  mounted() {
    const persistedAuth = localStorage.getItem('isAuthenticated')
    this.isAuthenticated = persistedAuth === 'true'
    window.dispatchEvent(new Event('auth-changed'))
  },
  methods: {
    clearFeedback() {
      this.errors.email = ''
      this.errors.password = ''
      this.status.type = ''
      this.status.message = ''
    },
    validateForm() {
      let isValid = true
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/

      if (!this.form.email) {
        this.errors.email = 'Informe seu e-mail.'
        isValid = false
      } else if (!emailRegex.test(this.form.email)) {
        this.errors.email = 'Digite um e-mail válido.'
        isValid = false
      }

      if (!this.form.password) {
        this.errors.password = 'Informe sua senha.'
        isValid = false
      } else if (this.form.password.length < 6) {
        this.errors.password = 'A senha deve ter pelo menos 6 caracteres.'
        isValid = false
      }

      return isValid
    },
    handleSubmit() {
      this.clearFeedback()
      if (!this.validateForm()) {
        this.status.type = 'error'
        this.status.message = 'Corrija os campos obrigatórios.'
        return
      }

      this.status.type = 'success'
      this.status.message = 'Login validado no front-end com sucesso!'
      this.isAuthenticated = true
      localStorage.setItem('isAuthenticated', 'true')
      window.dispatchEvent(new Event('auth-changed'))
    }
  }
}
</script>

<style>
#demo {
  max-width: 800px;
  max-height: 600px;
  margin: 0 auto;
  overflow: hidden;
}

#demo .carousel-inner img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.carousel-control-prev-icon,
.carousel-control-next-icon {
  filter: invert(100%);
}

.lora {
  font-family: "Lora", serif;
  font-optical-sizing: auto;
}

.card-img-top {
  width: 100%;
  height: 220px;
  object-fit: cover;
  transition: transform 0.4s ease-in-out;
}

.card-zoom {
  overflow: hidden;
}

.card-zoom:hover .card-img-top {
  transform: scale(1.08);
}

.card-body {
  display: flex;
  flex-direction: column;
  height: 260px;
}

.card-text {
  flex: 1;
  overflow: hidden;
}

.card-body .btn {
  margin-top: auto;
}

.caption-bg {
  background: rgba(0, 0, 0, 0.55);
  padding: 8px 16px;
  border-radius: 8px;
  font-size: 1.05rem;
  font-weight: bold;
}

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
