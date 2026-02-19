<template>
  <main class="container py-5">
    <section class="p-4 rounded-4 border">
      <h2 class="lora mb-2">Conteúdo extra: plano semanal de bem-estar</h2>
      <p class="text-muted mb-4">
        Uma sugestão simples para organizar hábitos que fortalecem sua saúde emocional durante a semana.
      </p>

      <div class="row g-3">
        <div class="col-md-4" v-for="item in plano" :key="item.dia">
          <article class="h-100 p-3 rounded-4 bg-light border">
            <h5 class="mb-2">{{ item.dia }}</h5>
            <p class="mb-0 text-muted">{{ item.atividade }}</p>
          </article>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>
const plano = [
  { dia: 'Segunda', atividade: '10 minutos de respiração consciente ao acordar.' },
  { dia: 'Terça', atividade: 'Caminhada leve de 20 minutos e hidratação reforçada.' },
  { dia: 'Quarta', atividade: 'Pausa sem telas por 30 minutos no fim do dia.' },
  { dia: 'Quinta', atividade: 'Conversar com alguém de confiança sobre sua semana.' },
  { dia: 'Sexta', atividade: 'Escrever 3 coisas positivas que aconteceram no dia.' },
  { dia: 'Fim de semana', atividade: 'Separar tempo para lazer, descanso e sono adequado.' }
]
</script>

<style scoped>
.lora {
  font-family: 'Lora', serif;
}
</style>
