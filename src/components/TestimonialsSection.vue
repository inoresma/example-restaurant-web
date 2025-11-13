<template>
  <section
    class="section-padding bg-gray-50"
  >
    <div class="container-custom">
      <h2 class="text-4xl md:text-5xl font-bold text-center text-gray-900 mb-12">
        Lo Que Dicen Nuestros Clientes
      </h2>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <TestimonialCard
          v-for="testimonial in testimonials"
          :key="testimonial.id"
          :testimonial="testimonial"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import TestimonialCard from './TestimonialCard.vue'

const testimonials = [
  {
    id: 1,
    name: 'María González',
    text: 'La mejor experiencia gastronómica italiana que he tenido. Los sabores auténticos y el ambiente acogedor hacen que cada visita sea especial. El servicio es impecable.'
  },
  {
    id: 2,
    name: 'Carlos Rodríguez',
    text: 'Increíble atención al detalle en cada plato. La pasta está perfectamente cocida y las salsas son excepcionales. Definitivamente volveré pronto con mi familia.'
  },
  {
    id: 3,
    name: 'Ana Martínez',
    text: 'Un verdadero tesoro culinario. La combinación de ingredientes frescos y técnicas tradicionales crea platos que son pura obra de arte. Altamente recomendado.'
  }
]
</script>

