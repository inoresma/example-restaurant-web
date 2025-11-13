<template>
  <footer class="bg-black text-white py-12">
    <div class="container-custom">
      <div class="flex flex-col md:flex-row items-center justify-between space-y-4 md:space-y-0">
        <div class="text-center md:text-left">
          <p class="text-gray-400">
            &copy; {{ currentYear }} La Buona Vita. Todos los derechos reservados.
          </p>
        </div>

        <div class="flex space-x-6">
          <a
            href="#"
            class="text-3xl hover:text-accent-orange transition-colors duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 rounded"
            aria-label="Facebook"
          >
            📘
          </a>
          <a
            href="#"
            class="text-3xl hover:text-accent-orange transition-colors duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 rounded"
            aria-label="Instagram"
          >
            📷
          </a>
          <a
            href="#"
            class="text-3xl hover:text-accent-orange transition-colors duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 rounded"
            aria-label="Twitter"
          >
            🐦
          </a>
          <a
            href="#"
            class="text-3xl hover:text-accent-orange transition-colors duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50 rounded"
            aria-label="TripAdvisor"
          >
            ⭐
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue'

const currentYear = computed(() => {
  return new Date().getFullYear()
})
</script>

