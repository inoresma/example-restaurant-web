<template>
  <section
    id="reservas"
    class="section-padding bg-gradient-to-br from-gray-900 via-gray-800 to-black"
  >
    <div class="container-custom">
      <h2 class="text-4xl md:text-5xl font-bold text-center text-white mb-12">
        Reserva Tu Mesa
      </h2>

      <div class="max-w-2xl mx-auto">
        <form
          @submit.prevent="handleSubmit"
          class="bg-white/10 backdrop-blur-md rounded-lg p-8 md:p-12 shadow-2xl"
        >
          <div class="grid md:grid-cols-2 gap-6 mb-6">
            <div>
              <label
                for="nombre"
                class="block text-white font-semibold mb-2"
              >
                Nombre Completo *
              </label>
              <input
                id="nombre"
                v-model="form.nombre"
                type="text"
                required
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white placeholder-gray-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                placeholder="Juan Pérez"
                aria-required="true"
              />
            </div>

            <div>
              <label
                for="email"
                class="block text-white font-semibold mb-2"
              >
                Email *
              </label>
              <input
                id="email"
                v-model="form.email"
                type="email"
                required
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white placeholder-gray-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                placeholder="juan@ejemplo.com"
                aria-required="true"
              />
            </div>
          </div>

          <div class="grid md:grid-cols-2 gap-6 mb-6">
            <div>
              <label
                for="telefono"
                class="block text-white font-semibold mb-2"
              >
                Teléfono *
              </label>
              <input
                id="telefono"
                v-model="form.telefono"
                type="tel"
                required
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white placeholder-gray-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                placeholder="+56 9 1234 5678"
                aria-required="true"
              />
            </div>

            <div>
              <label
                for="fecha"
                class="block text-white font-semibold mb-2"
              >
                Fecha *
              </label>
              <input
                id="fecha"
                v-model="form.fecha"
                type="date"
                required
                :min="minDate"
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                aria-required="true"
              />
            </div>
          </div>

          <div class="grid md:grid-cols-2 gap-6 mb-6">
            <div>
              <label
                for="hora"
                class="block text-white font-semibold mb-2"
              >
                Hora *
              </label>
              <input
                id="hora"
                v-model="form.hora"
                type="time"
                required
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                aria-required="true"
              />
            </div>

            <div>
              <label
                for="personas"
                class="block text-white font-semibold mb-2"
              >
                Número de Personas *
              </label>
              <select
                id="personas"
                v-model="form.personas"
                required
                class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all"
                aria-required="true"
              >
                <option value="" disabled class="text-gray-900">Selecciona...</option>
                <option v-for="num in 10" :key="num" :value="num" class="text-gray-900">
                  {{ num }} {{ num === 1 ? 'persona' : 'personas' }}
                </option>
              </select>
            </div>
          </div>

          <div class="mb-6">
            <label
              for="comentarios"
              class="block text-white font-semibold mb-2"
            >
              Comentarios Adicionales
            </label>
            <textarea
              id="comentarios"
              v-model="form.comentarios"
              rows="4"
              class="w-full px-4 py-3 rounded-lg bg-white/20 border border-white/30 text-white placeholder-gray-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 focus:border-accent-orange transition-all resize-none"
              placeholder="Alergias, preferencias especiales, ocasión especial..."
            ></textarea>
          </div>

          <button
            type="submit"
            class="w-full bg-accent-orange hover:bg-accent-gold text-white font-bold py-4 px-8 rounded-lg text-lg transform hover:scale-105 transition-all duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 shadow-lg"
          >
            Confirmar Reserva
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const form = ref({
  nombre: '',
  email: '',
  telefono: '',
  fecha: '',
  hora: '',
  personas: '',
  comentarios: ''
})

const minDate = computed(() => {
  const today = new Date()
  return today.toISOString().split('T')[0]
})

const handleSubmit = () => {
  alert('¡Reserva confirmada! Te hemos enviado un email de confirmación. Nos vemos pronto en La Buona Vita.')
  
  form.value = {
    nombre: '',
    email: '',
    telefono: '',
    fecha: '',
    hora: '',
    personas: '',
    comentarios: ''
  }
}
</script>

