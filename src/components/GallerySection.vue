<template>
  <section
    id="galeria"
    class="section-padding bg-white"
  >
    <div class="container-custom">
      <h2 class="text-4xl md:text-5xl font-bold text-center text-gray-900 mb-12">
        Galería
      </h2>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 md:gap-6">
        <div
          v-for="(image, index) in images"
          :key="index"
          class="relative overflow-hidden rounded-lg aspect-square group cursor-pointer"
          @mouseenter="handleHover(index)"
          @mouseleave="handleLeave(index)"
        >
          <img
            :src="image.url"
            :alt="image.alt"
            class="w-full h-full object-cover transition-transform duration-500"
            :class="{ 'scale-110': hoveredIndex === index }"
          />
          <div class="absolute inset-0 bg-black/0 group-hover:bg-black/20 transition-all duration-300"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const hoveredIndex = ref(null)

const images = [
  {
    url: 'https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=600&q=80',
    alt: 'Plato de pasta italiana'
  },
  {
    url: 'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=600&q=80',
    alt: 'Interior del restaurante'
  },
  {
    url: 'https://images.unsplash.com/photo-1555396273-367ea4eb4db5?w=600&q=80',
    alt: 'Ambiente del restaurante'
  },
  {
    url: 'https://images.unsplash.com/photo-1559339352-11d035aa65de?w=600&q=80',
    alt: 'Pizza italiana artesanal'
  },
  {
    url: 'https://images.unsplash.com/photo-1551218808-94e220e084d2?w=600&q=80',
    alt: 'Plato principal italiano'
  },
  {
    url: 'https://images.unsplash.com/photo-1556910103-1c02745aae4d?w=600&q=80',
    alt: 'Postre italiano'
  },
  {
    url: 'https://images.unsplash.com/photo-1526318896980-cf78c088247c?w=600&q=80',
    alt: 'Antipasto italiano'
  },
  {
    url: 'https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?w=600&q=80',
    alt: 'Risotto italiano'
  },
  {
    url: 'https://images.unsplash.com/photo-1476124369491-e7addf5db371?w=600&q=80',
    alt: 'Experiencia gastronómica'
  }
]

const handleHover = (index) => {
  hoveredIndex.value = index
}

const handleLeave = () => {
  hoveredIndex.value = null
}
</script>

