<template>
  <main class="container py-5">
    <div class="mx-auto form-wrapper">
      <h2 class="lora mb-2">Formulário de acompanhamento emocional</h2>
      <p class="text-muted mb-4">Preencha para registrar como você está hoje.</p>

      <form class="p-4 border rounded-4 bg-light" @submit.prevent="handleSubmit" novalidate>
        <div class="mb-3">
          <label for="nome" class="form-label fw-semibold">Nome</label>
          <input id="nome" v-model.trim="form.nome" type="text" class="form-control" required />
        </div>

        <div class="mb-3">
          <label for="email" class="form-label fw-semibold">E-mail</label>
          <input id="email" v-model.trim="form.email" type="email" class="form-control" required />
        </div>

        <div class="mb-3">
          <label for="humor" class="form-label fw-semibold">Como está seu humor hoje?</label>
          <select id="humor" v-model="form.humor" class="form-select" required>
            <option disabled value="">Selecione uma opção</option>
            <option>Bem</option>
            <option>Mais ou menos</option>
            <option>Mal</option>
          </select>
        </div>

        <div class="mb-3">
          <label for="mensagem" class="form-label fw-semibold">Observações</label>
          <textarea
            id="mensagem"
            v-model.trim="form.observacoes"
            class="form-control"
            rows="4"
            placeholder="Escreva um resumo do seu dia"
          ></textarea>
        </div>

        <button class="btn btn-primary" type="submit">Enviar formulário</button>
      </form>

      <div v-if="enviado" class="alert alert-success mt-3 mb-0">
        Formulário enviado com sucesso! Continue cuidando da sua saúde mental 💙
      </div>
    </div>
  </main>
</template>

<script setup>
import { reactive, ref } from 'vue'

const enviado = ref(false)

const form = reactive({
  nome: '',
  email: '',
  humor: '',
  observacoes: ''
})

const handleSubmit = () => {
  enviado.value = true
}
</script>

<style scoped>
.form-wrapper {
  max-width: 720px;
}

.lora {
  font-family: 'Lora', serif;
}
</style>
