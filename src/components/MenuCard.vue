<template>
  <div
    class="bg-white rounded-lg shadow-md overflow-hidden transform transition-all duration-300 hover:scale-105 hover:shadow-xl"
  >
    <div class="h-48 overflow-hidden">
      <img
        :src="dish.image"
        :alt="dish.name"
        class="w-full h-full object-cover"
      />
    </div>
    <div class="p-6">
      <h3 class="text-xl font-bold text-gray-900 mb-2">{{ dish.name }}</h3>
      <p class="text-gray-600 mb-4">{{ dish.description }}</p>
      <div class="flex items-center justify-between">
        <span class="text-2xl font-bold text-accent-orange">${{ dish.price }} CLP</span>
        <span class="text-sm text-gray-500 bg-gray-100 px-3 py-1 rounded-full">{{ dish.category }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  dish: {
    type: Object,
    required: true
  }
})
</script>

