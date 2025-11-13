<template>
  <section
    id="inicio"
    class="relative h-screen flex items-center justify-center overflow-hidden"
  >
    <div
      class="absolute inset-0 bg-cover bg-center bg-no-repeat"
      :style="{ backgroundImage: 'url(https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1920&q=80)' }"
      aria-hidden="true"
    ></div>
    <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/60 to-black/80"></div>

    <div class="relative z-10 text-center px-4 max-w-4xl mx-auto">
      <h1
        class="text-5xl md:text-7xl font-bold text-white mb-6 animate-fade-in-up"
        style="animation-delay: 0.2s; opacity: 0;"
      >
        Bienvenido a La Buona Vita
      </h1>
      <p
        class="text-xl md:text-2xl text-gray-200 mb-8 animate-fade-in-up"
        style="animation-delay: 0.4s; opacity: 0;"
      >
        Auténtica cocina italiana en el corazón de la ciudad
      </p>
      <button
        @click="scrollToReservations"
        class="bg-accent-orange hover:bg-accent-gold text-white font-semibold py-4 px-8 rounded-lg text-lg transform hover:scale-105 hover:shadow-2xl transition-all duration-300 animate-fade-in-up focus:outline-none focus:ring-4 focus:ring-accent-orange/50"
        style="animation-delay: 0.6s; opacity: 0;"
        aria-label="Reservar una mesa"
      >
        Reservar Mesa
      </button>
    </div>
  </section>
</template>

<script setup>
const scrollToReservations = () => {
  const element = document.getElementById('reservas')
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top
    const offsetPosition = elementPosition + window.pageYOffset - offset

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
}
</script>

