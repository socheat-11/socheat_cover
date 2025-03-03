<template>
    <div class="bg-[]">
        <section class="max-w-screen-xl mx-auto p-4 py-10" id="blog">

            <div class="flex flex-wrap items-center justify-between px-4 py-2">
                <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
                    <span class="relative inline-block">
                        Blog or News
                        <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
                    </span>
                </h1>

                <button
                    class="text-[#15b8a6] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                    <span class="relative z-0">Hire Me</span>
                </button>
            </div>

            <div class="grid mt-5 grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                <div data-aos="zoom-in-down" data-aos-duration="2000" class="p-4" v-for="(blog, index) in blogtest"
                    :key="index">
                    <div class="">
                        <img :src="blog.image" :alt="blog.title" class="w-full h-auto rounded-md ">
                    </div>
                    <div class="flex mt-3 justify-start items-center space-x-3">
                        <p class="text-[15px] text-gray-400">
                            <FontAwesomeIcon class="text-[13px] text-[#15b8a6]" :icon="faCalendar" /> 13th March 2023
                        </p>
                        <p class="text-[15px] text-gray-400">
                            <FontAwesomeIcon class="text-[13px] text-[#15b8a6]" :icon="faClock" /> 5 min read
                        </p>
                    </div>
                    <h3 class="text-[18px] mt-3 font-bold"> {{ blog.title }}</h3>
                    <p class="mt-3 text-[15px] font-normal text-gray-400">{{ blog.description }}</p>

                    <button
                        class="mt-5 text-[#15b8a6] text-[15px] font-light transition duration-300 ease-in-out flex items-center gap-2">
                        Read More
                        <FontAwesomeIcon class="text-[10px] text-[#15b8a6]" :icon="faChevronRight" />
                    </button>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup>
    import { onMounted, ref } from 'vue';
    import AOS from 'aos';
    import 'aos/dist/aos.css';
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    import { faCalendar, faChevronRight, faClock } from '@fortawesome/free-solid-svg-icons';
    import img1 from "../assets/1.jpg";
    import img2 from "../assets/2.jpg";
    import img3 from "../assets/3.jpg";

    onMounted(() => {
        AOS.init();
    });

    const blogtest = ref([
        { 
            image: img1, 
            title: "Design your apps in your own way", 
            description: "This is required when, for example, the final text is not yet available."
        },
        {
            image: img2,
            title: "How apps is changing the IT world",
            description: "This is required when, for example, the final text is not yet available."
        },
        { 
            image: img3, 
            title: "Smartest Applications for Business", 
            description: "This is required when, for example, the final text is not yet available."
        },
    ]);
</script>
