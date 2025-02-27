<template>
  <div class="bg-[#ffffff]">
  
    <!-- Navbar -->
    <NavBar />

    <!-- Main Content -->
    <div>
      <section id="hero">
        <HeroSection />
      </section>
      <section id="about">
        <AboutSection />
      </section>
      <section id="services">
        <ServicesSection />
      </section>
    </div>

    <BackTotop />

    <Loading />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import BackTotop from './components/BackTotop.vue'
import Loading from './components/Loading.vue'

</script>

<style>

*{
  scrollbar-width: thin;
  scrollbar-color: #15b8a6 #f1f1f1;
  scroll-behavior: smooth;
  
}
</style>
