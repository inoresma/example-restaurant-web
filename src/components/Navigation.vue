<template>
  <nav
    class="fixed top-0 left-0 right-0 z-50 bg-black/80 backdrop-blur-custom transition-all duration-300"
    role="navigation"
    aria-label="Navegación principal"
  >
    <div class="container-custom">
      <div class="flex items-center justify-between h-20">
        <div class="flex items-center">
          <a
            href="#inicio"
            @click.prevent="scrollToSection('inicio')"
            class="text-2xl font-bold text-white hover:text-accent-orange transition-colors duration-300"
            aria-label="Ir al inicio"
          >
            La Buona Vita
          </a>
        </div>

        <button
          @click="toggleMobileMenu"
          class="md:hidden text-white p-2 focus:outline-none focus:ring-2 focus:ring-accent-orange rounded"
          aria-label="Abrir menú móvil"
          aria-expanded="mobileMenuOpen"
        >
          <svg
            v-if="!mobileMenuOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <svg
            v-else
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>

        <ul
          :class="[
            'md:flex md:items-center md:space-x-8 space-y-4 md:space-y-0',
            mobileMenuOpen ? 'flex flex-col absolute top-20 left-0 right-0 bg-black/95 backdrop-blur-custom p-6' : 'hidden'
          ]"
        >
          <li v-for="item in menuItems" :key="item.id">
            <a
              :href="`#${item.id}`"
              @click.prevent="scrollToSection(item.id)"
              class="text-white hover:text-accent-orange transition-colors duration-300 font-medium focus:outline-none focus:ring-2 focus:ring-accent-orange rounded px-2 py-1"
              :aria-label="`Ir a ${item.label}`"
            >
              {{ item.label }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const menuItems = [
  { id: 'inicio', label: 'Inicio' },
  { id: 'sobre-nosotros', label: 'Sobre Nosotros' },
  { id: 'menu', label: 'Menú' },
  { id: 'galeria', label: 'Galería' },
  { id: 'reservas', label: 'Reservas' },
  { id: 'contacto', label: 'Contacto' },
]

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top
    const offsetPosition = elementPosition + window.pageYOffset - offset

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
  mobileMenuOpen.value = false
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

