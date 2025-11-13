<template>
  <section
    id="contacto"
    class="section-padding bg-white"
  >
    <div class="container-custom">
      <h2 class="text-4xl md:text-5xl font-bold text-center text-gray-900 mb-12">
        Contacto
      </h2>

      <div class="grid md:grid-cols-2 gap-12">
        <div class="space-y-6">
          <div class="bg-gray-50 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300">
            <div class="flex items-start space-x-4">
              <span class="text-4xl" aria-hidden="true">📍</span>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Dirección</h3>
                <p class="text-gray-700">
                  Av. Providencia 1234<br>
                  Providencia, Santiago, Chile
                </p>
              </div>
            </div>
          </div>

          <div class="bg-gray-50 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300">
            <div class="flex items-start space-x-4">
              <span class="text-4xl" aria-hidden="true">📞</span>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Teléfono</h3>
                <a
                  href="tel:+56912345678"
                  class="text-gray-700 hover:text-accent-orange transition-colors duration-300"
                >
                  +56 9 1234 5678
                </a>
              </div>
            </div>
          </div>

          <div class="bg-gray-50 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300">
            <div class="flex items-start space-x-4">
              <span class="text-4xl" aria-hidden="true">📧</span>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Email</h3>
                <a
                  href="mailto:info@labuonavita.com"
                  class="text-gray-700 hover:text-accent-orange transition-colors duration-300"
                >
                  info@labuonavita.com
                </a>
              </div>
            </div>
          </div>

          <div class="bg-gray-50 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300">
            <div class="flex items-start space-x-4">
              <span class="text-4xl" aria-hidden="true">🕐</span>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Horarios</h3>
                <div class="text-gray-700 space-y-1">
                  <p><span class="font-semibold">Lunes - Jueves:</span> 12:00 PM - 10:00 PM</p>
                  <p><span class="font-semibold">Viernes - Sábado:</span> 12:00 PM - 11:00 PM</p>
                  <p><span class="font-semibold">Domingo:</span> 1:00 PM - 9:00 PM</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="h-96 md:h-[500px] rounded-lg overflow-hidden shadow-2xl">
          <div class="w-full h-full bg-gradient-to-br from-gray-300 via-gray-400 to-gray-500 flex items-center justify-center">
            <div class="text-center text-gray-600">
              <span class="text-6xl mb-4 block" aria-hidden="true">🗺️</span>
              <p class="text-xl font-semibold">Mapa</p>
              <p class="text-sm mt-2">Av. Providencia 1234<br>Providencia, Santiago, Chile</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

