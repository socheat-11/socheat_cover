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

      <section id="testimonial">
        <TestimonialSection />
      </section>

      <section id="pricing">
        <Pricing />
      </section>
      <section id="blog">
        <Blog />
      </section>

      <section id="contact">
        <Contact />
      </section>

    </div>
    <Footer />
    <BackTotop />

    <Loading />
  </div>
</template>

<script setup>
  import NavBar from './components/NavBar.vue'
  import HeroSection from './components/HeroSection.vue'
  import AboutSection from './components/AboutSection.vue'
  import ServicesSection from './components/ServicesSection.vue'
  import TestimonialSection from './components/TestimonialSection.vue'
  import BackTotop from './components/BackTotop.vue'
  import Loading from './components/Loading.vue'
  import Pricing from './components/Pricing.vue'
  import Blog from './components/Blog.vue'
  import Contact from './components/contact.vue'
  import Footer from './components/Footer.vue'
</script>

<style>
  * {
    scrollbar-width: thin;
    scrollbar-color: #15b8a6 #f1f1f1;
    scroll-behavior: smooth;

  }
</style>