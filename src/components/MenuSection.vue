<template>
  <section
    id="menu"
    class="section-padding bg-gray-50"
  >
    <div class="container-custom">
      <h2 class="text-4xl md:text-5xl font-bold text-center text-gray-900 mb-12">
        Nuestro Menú
      </h2>

      <div class="flex flex-wrap justify-center gap-4 mb-12">
        <button
          v-for="category in categories"
          :key="category"
          @click="filterByCategory(category)"
          :class="[
            'px-6 py-3 rounded-full font-semibold transition-all duration-300 focus:outline-none focus:ring-4 focus:ring-accent-orange/50',
            activeCategory === category
              ? 'bg-accent-orange text-white shadow-lg transform scale-105'
              : 'bg-white text-gray-700 hover:bg-gray-100'
          ]"
          :aria-label="`Filtrar por ${category}`"
        >
          {{ category }}
        </button>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <MenuCard
          v-for="dish in filteredDishes"
          :key="dish.id"
          :dish="dish"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'
import MenuCard from './MenuCard.vue'

const activeCategory = ref('Todos')

const categories = ['Todos', 'Entradas', 'Pasta', 'Platos Principales', 'Postres']

const dishes = [
  {
    id: 1,
    name: 'Bruschetta al Pomodoro',
    description: 'Pan tostado con tomates frescos, ajo, albahaca y aceite de oliva extra virgen',
    price: '7.500',
    category: 'Entradas',
    image: 'https://images.unsplash.com/photo-1526318896980-cf78c088247c?w=400&q=80'
  },
  {
    id: 2,
    name: 'Spaghetti Carbonara',
    description: 'Pasta tradicional con pancetta, huevo, queso pecorino y pimienta negra',
    price: '14.500',
    category: 'Pasta',
    image: 'https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?w=400&q=80'
  },
  {
    id: 3,
    name: 'Risotto ai Funghi',
    description: 'Arroz cremoso con setas silvestres, vino blanco y queso parmesano',
    price: '16.000',
    category: 'Platos Principales',
    image: 'https://images.unsplash.com/photo-1476124369491-e7addf5db371?w=400&q=80'
  },
  {
    id: 4,
    name: 'Osso Buco alla Milanese',
    description: 'Estofado de jarrete de ternera con verduras, vino blanco y gremolata',
    price: '22.900',
    category: 'Platos Principales',
    image: 'https://images.unsplash.com/photo-1546833999-b9f581a1996d?w=400&q=80'
  },
  {
    id: 5,
    name: 'Tiramisú Classico',
    description: 'Postre tradicional con café, mascarpone, cacao y bizcochos de soletilla',
    price: '6.800',
    category: 'Postres',
    image: 'https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?w=400&q=80'
  },
  {
    id: 6,
    name: 'Panna Cotta',
    description: 'Postre cremoso de vainilla con salsa de frutos rojos',
    price: '6.200',
    category: 'Postres',
    image: 'https://images.unsplash.com/photo-1551024506-0bccd828d307?w=400&q=80'
  },
  {
    id: 7,
    name: 'Lasagna della Nonna',
    description: 'Lasaña casera con carne, bechamel y queso mozzarella',
    price: '15.200',
    category: 'Pasta',
    image: 'https://images.unsplash.com/photo-1574894709920-11b28e7367e3?w=400&q=80'
  },
  {
    id: 8,
    name: 'Antipasto Misto',
    description: 'Selección de embutidos italianos, quesos y verduras encurtidas',
    price: '11.500',
    category: 'Entradas',
    image: 'https://images.unsplash.com/photo-1504674900247-0877df9cc836?w=400&q=80'
  },
  {
    id: 9,
    name: 'Penne all\'Arrabbiata',
    description: 'Pasta con salsa de tomate picante, ajo y perejil fresco',
    price: '13.000',
    category: 'Pasta',
    image: 'https://images.unsplash.com/photo-1551183053-bf91a1d81141?w=400&q=80'
  }
]

const filteredDishes = computed(() => {
  if (activeCategory.value === 'Todos') {
    return dishes
  }
  return dishes.filter(dish => dish.category === activeCategory.value)
})

const filterByCategory = (category) => {
  activeCategory.value = category
}
</script>

