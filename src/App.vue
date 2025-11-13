<template>
  <div id="app">
    <Navigation />
    <HeroSection />
    <AboutSection />
    <MenuSection />
    <GallerySection />
    <TestimonialsSection />
    <ReservationsSection />
    <ContactSection />
    <Footer />
  </div>
</template>

<script setup>
import Navigation from './components/Navigation.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import MenuSection from './components/MenuSection.vue'
import GallerySection from './components/GallerySection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import ReservationsSection from './components/ReservationsSection.vue'
import ContactSection from './components/ContactSection.vue'
import Footer from './components/Footer.vue'
</script>

<style scoped>
#app {
  @apply min-h-screen;
}
</style>

