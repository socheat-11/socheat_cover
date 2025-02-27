<template>
    <div class="bg-[#f5fbfa]">
        <section class="max-w-screen-xl mx-auto" id="about">
            <div class="flex flex-wrap py-10">
                <div class="w-full md:w-1/2 p-4 ">
                    <div data-aos="zoom-in-down" data-aos-duration="2000"
                        class="relative flex justify-center items-center w-full max-w-md mx-auto">
                        <!-- Image -->
                        <img src="../assets/about.jpg" alt="Experience" class="w-full rounded-full">

                        <!-- Centered Text Box -->
                        <div class="absolute flex flex-col group justify-center items-center bg-white w-40 h-40 rounded-full shadow-lg
           transition-transform duration-500 ease-in-out transform hover:scale-110 hover:shadow-xl">
                            <span class="text-3xl font-bold group-hover:text-[#15b8a6] text-teal-600">15+</span>
                            <span class="text-sm font-semibold group-hover:text-[#15b8a6] text-gray-700">Years</span>
                            <span
                                class="text-sm font-semibold group-hover:text-[#15b8a6] text-gray-700">Experience</span>
                        </div>

                    </div>

                </div>
                <div class="w-full md:w-1/2 p-4 flex items-center justify-center">
                    <div data-aos="zoom-in-down" data-aos-duration="2000" class="flex flex-col">
                        <h2 class="text-[#15b8a6] text-[15px] font-semibold uppercase">Who Are We ?</h2>
                        <h2 class="text-[25px] mt-3 text-black font-semibold">
                            We're a global stakeholder <br>
                            relations and partnership <br>
                            building consultancy.
                        </h2>
                        <h3 class="text-gray-400 mt-3 font-normal text-[15px] ">
                            Get instant helpful resources about anything on the go, easily implement secure money transfer solutions, boost your daily efficiency, connect to other app users and create your own Techwind network, and much more with just a few taps. commodo consequat. Duis aute irure.
                        </h3>
                        <div>
                            <button
                                class="bg-[#15b8a6] mt-5 px-5 py-3 text-white font-semibold rounded-lg hover:bg-[#13a394] transition duration-300 ease-in-out flex items-center gap-2">
                                Contact Us
                                <FontAwesomeIcon class="text-[10px]" :icon="faChevronRight" />
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup>
    import {
        onMounted
    } from 'vue';
    import AOS from 'aos';
    import 'aos/dist/aos.css';
    import {
        FontAwesomeIcon
    } from '@fortawesome/vue-fontawesome';
    import {
        faChevronRight
    } from '@fortawesome/free-solid-svg-icons';
    onMounted(() => {
        AOS.init();
    });
</script>