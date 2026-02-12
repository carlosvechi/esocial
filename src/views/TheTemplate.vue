<template>
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
    <!-- Indicators -->
    <div class="carousel-indicators">
      <button type="button" data-bs-target="#demo" data-bs-slide-to="0" class="active sb"></button>
      <button type="button" data-bs-target="#demo" data-bs-slide-to="1" class="sb"></button>
      <button type="button" data-bs-target="#demo" data-bs-slide-to="2" class="sb"></button>
    </div>

    <!-- Slides -->
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="../assets/cuidado.png" alt="Autocuidado" class="d-block w-100" />
        <div class="carousel-caption caption-bg">
          Autocuidado: pequenas práticas, grandes mudanças
        </div>
      </div>

      <div class="carousel-item">
        <img src="../assets/rotina.png" alt="Ansiedade e rotina" class="d-block w-100" />
        <div class="carousel-caption caption-bg">
          Prevenção da ansiedade: rotina, sono e limites
        </div>
      </div>

      <div class="carousel-item">
        <img src="../assets/apoio.png" alt="Apoio psicológico" class="d-block w-100" />
        <div class="carousel-caption caption-bg">
          Apoio psicológico: pedir ajuda é coragem
        </div>
      </div>
    </div>

    <!-- Controls -->
    <button class="carousel-control-prev" type="button" data-bs-target="#demo" data-bs-slide="prev">
      <span class="carousel-control-prev-icon"></span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#demo" data-bs-slide="next">
      <span class="carousel-control-next-icon"></span>
    </button>
  </div>

  <!-- Cards -->
  
  <!-- Seção: Prevenção -->
  <section id="prevencao" class="container mt-5">
    <div class="p-4 rounded-4 border">
      <h3 class="lora mb-3">Prevenção da ansiedade e depressão</h3>

      <div class="row g-3">
        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Rotina e sono</strong>
            <p class="mb-0 text-muted">
              Dormir bem regula humor e energia. Tente manter horários mais consistentes (inclusive no fim de semana).
            </p>
          </div>
        </div>

        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Redução de estresse</strong>
            <p class="mb-0 text-muted">
              Respiração, pausas e “limites” (falar não) ajudam a reduzir sobrecarga mental no dia a dia.
            </p>
          </div>
        </div>

        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Rede de apoio</strong>
            <p class="mb-0 text-muted">
              Conversar com alguém de confiança já é um passo. Isolamento costuma piorar sintomas.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção: Autocuidado -->
  <section id="autocuidado" class="container mt-5">
    <div class="p-4 rounded-4 border bg-light">
      <h3 class="lora mb-3">Autocuidado e bem-estar emocional</h3>

      <div class="row g-3">
        <div class="col-md-6">
          <div class="p-3 rounded-4 bg-white border h-100">
            <strong>Checklist simples (diário)</strong>
            <ul class="mb-0 text-muted mt-2">
              <li>Beber água e comer algo decente</li>
              <li>10–20 min de movimento (caminhar já vale)</li>
              <li>Uma pausa sem tela</li>
              <li>Uma coisa prazerosa (música, hobby, leitura)</li>
            </ul>
          </div>
        </div>

        <div class="col-md-6">
          <div class="p-3 rounded-4 bg-white border h-100">
            <strong>Autocompaixão</strong>
            <p class="mb-0 text-muted mt-2">
              Não é “ser fraco”. É reconhecer limites. Troque “eu não consigo” por “eu estou tentando e posso pedir ajuda”.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção: Apoio Psicológico -->
  <section id="apoio" class="container mt-5">
    <div class="p-4 rounded-4 border">
      <h3 class="lora mb-3">Apoio psicológico</h3>

      <div class="row g-3">
        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Quando buscar ajuda?</strong>
            <p class="mb-0 text-muted">
              Se sintomas persistirem por semanas, atrapalharem rotina, sono, trabalho ou estudos.
            </p>
          </div>
        </div>

        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Terapia</strong>
            <p class="mb-0 text-muted">
              Ajuda a entender pensamentos, emoções e comportamentos. É um espaço seguro e sem julgamento.
            </p>
          </div>
        </div>

        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Como apoiar alguém</strong>
            <p class="mb-0 text-muted">
              Escute, valide sentimentos, evite “é só…” e ofereça ajuda prática (acompanhar, pesquisar serviços, etc.).
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção: Combate ao estigma -->
  <section id="estigma" class="container mt-5">
    <div class="p-4 rounded-4 border bg-light">
      <h3 class="lora mb-2">Combate ao estigma</h3>
      <p class="mb-3 text-muted">
        Transtornos mentais não são “fraqueza” nem “frescura”. Falar sobre isso com respeito salva vidas.
      </p>

      <div class="row g-3">
        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-white border h-100">
            <strong>Use linguagem respeitosa</strong>
            <p class="mb-0 text-muted">Evite piadas e rótulos. Foque na pessoa, não no diagnóstico.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-white border h-100">
            <strong>Incentive busca de ajuda</strong>
            <p class="mb-0 text-muted">Terapia e acompanhamento médico são formas de cuidado, não vergonha.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="p-3 rounded-4 bg-white border h-100">
            <strong>Escute sem julgar</strong>
            <p class="mb-0 text-muted">Às vezes a melhor ajuda é presença + escuta de verdade.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção: Canais de ajuda -->
  <section id="ajuda" class="container mt-5 mb-5">
    <div class="p-4 rounded-4 border">
      <h3 class="lora mb-3">Canais de ajuda</h3>
      <p class="text-muted mb-3">
        Se você estiver em sofrimento intenso, procure ajuda imediatamente. Se for emergência, busque um serviço local.
      </p>

      <div class="row g-3">
        <div class="col-md-6">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>CVV (Centro de Valorização da Vida)</strong>
            <p class="mb-2 text-muted">Apoio emocional e prevenção do suicídio (atendimento 24h, dependendo do canal).</p>
            <span class="badge text-bg-dark">Ligue 188</span>
          </div>
        </div>

        <div class="col-md-6">
          <div class="p-3 rounded-4 bg-light border h-100">
            <strong>Rede pública e profissionais</strong>
            <p class="mb-0 text-muted">
              Procure UBS/serviços de saúde da sua cidade e, se possível, psicólogo(a) ou psiquiatra.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {}
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
</style>
