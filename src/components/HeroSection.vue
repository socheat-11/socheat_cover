<template>
    <div class="bg-[#f5fbfa] py-28">
        <section class="max-w-screen-xl mx-auto" id="hero">
            <div class="flex flex-wrap py-10">
                <div class="w-full md:w-1/2 p-4 flex items-center justify-center">
                    <div data-aos="zoom-in-down" data-aos-duration="2000" class="flex flex-col">
                        <h2 class="text-[40px] text-[#002d5b] font-bold">Hello 👋 I'am Front-End Develper  <br>​​<span class="text-[#15b8a6]">And Web Develper</span> </h2>
                        
                        <p class="text-start leading-7 font-light">
                        Hi, I'm <span class="font-normal text-[#002d5b]">Kin Socheat</span>, a passionate
                        <span class="text-[#002d5b] font-normal">Frontend Web Developer</span> and
                        <span class="text-[#002d5b] font-normal">Freelancer</span>.
                        I specialize in building responsive, user-friendly, and modern websites using
                        <span class="font-normal text-[#002d5b]">HTML, Tailwind CSS, Bootstrap, JavaScript,
                            Angular,
                            ReactJs, and Laravel</span>.
                        With a strong foundation in frontend technologies, I strive to create seamless
                        and visually appealing web experiences.
                    </p>
                        <div class="flex justify-start mt-5 items-center space-x-3 ">
                        <!-- Added flex-wrap for responsiveness -->
                        <button
                            class="text-[#fff] rounded-[4px] relative h-[50px] w-40 overflow-hidden bg-[#15b8a6] border border-[#15b8a6]  px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                            <span class="relative z-0">Download CV</span>
                        </button>
                        <button
                            class="text-black rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                            <span class="relative z-0">Hire Me</span>
                        </button>
                    </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faChevronRight } from '@fortawesome/free-solid-svg-icons';

onMounted(() => {
    AOS.init();
});
</script>