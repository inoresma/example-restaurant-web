<template>
  <div class="bg-white rounded-lg shadow-lg p-8 h-full flex flex-col">
    <div class="flex items-center mb-4">
      <span
        v-for="i in 5"
        :key="i"
        class="text-2xl text-accent-gold"
        aria-label="5 estrellas"
      >
        ★
      </span>
    </div>
    <p class="text-gray-700 text-lg mb-6 flex-grow italic">
      "{{ testimonial.text }}"
    </p>
    <div class="border-t pt-4">
      <p class="font-semibold text-gray-900 text-lg">{{ testimonial.name }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  testimonial: {
    type: Object,
    required: true
  }
})
</script>

