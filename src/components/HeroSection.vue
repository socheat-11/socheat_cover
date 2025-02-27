<template>
    <div class="bg-[#f5fbfa] py-24">
        <section class="max-w-screen-xl mx-auto mt-18" id="about">
            <div class="flex flex-wrap">
                <div class="w-full md:w-1/2 p-4 flex items-center justify-center">
                    <div  data-aos="zoom-in-down" data-aos-duration="2000" class="flex flex-col">
                        <h2 class="text-[45px] text-black font-bold">Get Creative & <br> Modern With Upcover</h2>
                        <h3 class="text-gray-400 font-normal text-lg leading-relaxed">
                            This is just a simple text made for this unique and
                            awesome template, you can replace it with any text.
                        </h3>
                        <div>
                            <button
                                class="bg-[#15b8a6] mt-5 px-6 py-3 text-white font-semibold rounded-lg hover:bg-[#13a394] shadow-lg transition duration-300 ease-in-out flex items-center gap-2">
                                Contact Us
                                <FontAwesomeIcon class="text-[10px]" :icon="faChevronRight" />
                            </button>
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/2 p-4">
                    <div  data-aos="zoom-in-down" data-aos-duration="2000"  
                        class="flex py-32 justify-center rounded-full items-center bg-[#ddf8f4]">
                        <!-- Image -->
                        <img src="../assets/bg.png" alt="" class="max-w-xs md:max-w-md lg:max-w-lg z-10">
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
