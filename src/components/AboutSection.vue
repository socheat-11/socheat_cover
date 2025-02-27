<template>
    <div>
      <section class="max-w-screen-xl mx-auto text-center p-4 mt-2">
        <div data-aos="fade-up" data-aos-duration="2000" class="flex flex-wrap items-center justify-between px-4 py-2">
          <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
            <span class="relative inline-block">
              About Me
              <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#002d5b] -translate-x-1/2"></span>
            </span>
          </h1>
  
          <button
            class="text-[#002d5b] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#025198] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#025198] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
            <span class="relative z-0">Hire Me</span>
          </button>
        </div>
  
        <div class="py-5">
          <div class="flex space-x-4 flex-col md:flex-row">
            <!-- Profile Image -->
            <div data-aos="fade-up" data-aos-duration="2000" class="w-full md:w-1/2 flex flex-col items-center text-center">
              <div class="bg-[#15b8a6] w-[250px] sm:w-[280px] md:w-[300px] rounded flex justify-center items-center p-4">
                <img src="../assets/scoheat1.png" alt="Kin Socheat" class="w-[250px] sm:w-[280px] md:w-[300px] lg:w-[320px] relative lg:-right-16 lg:-bottom-8 bg-[#e8f3f4] rounded transition-all duration-300 hover:scale-105">
              </div>
            </div>
  
            <!-- Profile Information -->
            <div data-aos="fade-up" data-aos-duration="2000" class="w-full md:w-1/2 sm:mt-5">
              <h2 class="text-[22px] text-start text-[#002d5b] font-bold">My Profile</h2>
              <p class="text-start leading-7 font-light">
                Hi, I'm <span class="font-normal">Kin Socheat</span>, a Computer Science student at the
                <span class="text-[#002d5b] font-normal">Royal University of Phnom Penh</span>.
                I started my studies in <span class="text-[#002d5b] font-normal">2022</span> and will
                graduate in <span class="text-[#002d5b] font-normal">2025</span>.
                I have a strong passion for <span class="font-normal text-[#002d5b]">front-end development</span>
                and web technologies, focusing on building responsive and efficient web applications.
              </p>
  
              <div class="mt-5 flex flex-wrap items-center gap-3">
                <div class="flex justify-start items-start space-x-2">
                  <div>
                    <h3 class="font-bold text-start text-[#002d5b] text-lg">15+</h3>
                    <h3 class="text-sm text-[#002d5b] text-start">Complete Projects</h3>
                  </div>
                </div>
                <div class="flex justify-start items-start space-x-2">
                  <div>
                    <h3 class="font-bold text-start text-[#002d5b] text-lg">30+</h3>
                    <h3 class="text-sm text-[#002d5b] text-start">Project not Complets</h3>
                  </div>
                </div>
                <div class="flex justify-start items-start space-x-2">
                  <div>
                    <h3 class="font-bold text-start text-[#002d5b] text-lg">1+</h3>
                    <h3 class="text-sm text-[#002d5b] text-start">Year of experiences</h3>
                  </div>
                </div>
              </div>
  
              <!-- Social Media Icons -->
              <div class="flex justify-start items-center mt-5 space-x-3">
                <a href="https://web.facebook.com/cheat.cheat.7169" aria-label="Facebook" class="group">
                  <FontAwesomeIcon :icon="['fab', 'facebook']"
                    class="text-[15px] shadow-md bg-[#fef9f9] hover:bg-[#15b8a6] hover:text-white rounded-full p-4 text-[#002d5b] transition duration-300 ease-in-out" />
                </a>
                <a href="https://www.linkedin.com/in/kin-socheat-30100b327/" aria-label="LinkedIn" class="group">
                  <FontAwesomeIcon :icon="['fab', 'linkedin']"
                    class="text-[15px] shadow-md bg-[#fef9f9] hover:bg-[#15b8a6] hover:text-white rounded-full p-4 text-[#002d5b] transition duration-300 ease-in-out" />
                </a>
                <a href="https://t.me/socheat_kin" aria-label="Telegram" class="group">
                  <FontAwesomeIcon :icon="['fab', 'telegram']"
                    class="text-[15px] shadow-md bg-[#fef9f9] hover:bg-[#15b8a6] hover:text-white rounded-full p-4 text-[#002d5b] transition duration-300 ease-in-out" />
                </a>
              </div>
  
              <!-- Hire Me Button -->
              <div class="flex justify-start mt-5 items-center">
                <button
                  class="text-[#15b8a6] rounded-[4px] relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                  <span class="relative z-10">Hire Me</span>
                </button>
              </div>
            </div>
          </div>
        </div>
      </section>
      <Experiences />
    </div>
  </template>
  
  <script setup>
    import { onMounted } from 'vue';
    import AOS from 'aos';
    import 'aos/dist/aos.css';
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    import { library } from '@fortawesome/fontawesome-svg-core';
    import { faFacebook, faLinkedin, faTelegram } from '@fortawesome/free-brands-svg-icons';
    import Experiences from './Experiences.vue';
  
    // Add FontAwesome icons to the library
    library.add(faFacebook, faLinkedin, faTelegram);
  
    onMounted(() => {
      AOS.init();
    });
  </script>
  
  <style scoped>
    /* Add any custom styles here */
  </style>
  