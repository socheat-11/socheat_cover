<template>
    <div class="py-5]">
      <section class="max-w-screen-xl mx-auto p-4 py-10" id="service">
        <div class="flex flex-wrap items-center justify-between px-4 py-2">
            <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
              <span class="relative inline-block">
                Services
                <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
              </span>
            </h1>
  
            <button
              class="text-[#15b8a6] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
              <span class="relative z-0">Hire Me</span>
            </button>
          </div>

  
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 mt-5 gap-4">
          <div v-for="(service, index) in services" :key="index"
            class="bg-white shadow-[0px_0px_6px_2px_#edf2f7] group p-4 py-8 rounded-lg text-start"
            data-aos="zoom-in-down" data-aos-duration="2000">
            <!-- Dynamic Icon Box -->
            <div class="bg-[#eff9f8] group-hover:bg-[#15b8a6] h-12 w-12 flex items-center justify-center rounded-full mb-5">
              <font-awesome-icon :icon="service.icon" class="text-teal-600 group-hover:text-[#eff9f8] text-lg" />
            </div>
  
            <!-- Service Title & Description -->
            <h3 class="text-[19px] mt-5 font-semibold text-black">{{ service.title }}</h3>
            <p class="text-[15px] mt-5 text-gray-400 font-normal">{{ service.description }}</p>
  
            <button class="mt-5 text-[#15b8a6] text-[15px] font-light transition duration-300 ease-in-out flex items-center gap-2">
              Read More
              <FontAwesomeIcon class="text-[10px] text-[#15b8a6]" :icon="faChevronRight" />
            </button>
          </div>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
  import { faCode, faChevronRight } from '@fortawesome/free-solid-svg-icons';

  
  // Initialize AOS animation
  onMounted(() => {
    AOS.init();
  });
  

  const services = ref([
  {
    title: "Freelancer",
    description: "Crafting modern and responsive user interfaces with cutting-edge front-end technologies.",
    icon: faCode,
  },
  {
    title: "Frontend Developer",
    description: "Crafting modern and responsive user interfaces with cutting-edge front-end technologies.",
    icon: faCode,
  },
  {
    title: "Web Development",
    description: "Building scalable and efficient websites with optimized performance and best practices.",
    icon: faCode,
  },
  {
    title: "Full Stack Developer",
    description: "Developing complete web applications with seamless front-end and back-end integration.",
    icon: faCode,
  },

]);

  </script>
  