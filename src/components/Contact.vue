<template>
    <div class="max-w-screen-xl mx-auto p-4 py-10" id="contact">

        <div class="flex flex-wrap items-center justify-between px-4 py-2">
            <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
                <span class="relative inline-block">
                    Contact
                    <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
                </span>
            </h1>

            <button
                class="text-[#15b8a6] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                <span class="relative z-0">Hire Me</span>
            </button>
        </div>

        <div class="flex flex-wrap mt-5">
            <!-- First column: full-width on small screens, half-width on medium and larger screens -->
            <div class="w-full md:w-1/2 p-4">
                <div data-aos="zoom-in-down" data-aos-duration="2000">
                    <img src="https://upcover-shreethemes.vercel.app/static/media/contact.adff68c5dcc9005ceb1a5566aaf4440b.svg"
                        alt="">
                </div>
            </div>

            <!-- Second column: full-width on small screens, half-width on medium and larger screens -->
            <div class="w-full md:w-1/2 p-4">
                <form  @submit.prevent="submitForm">
                    <div data-aos="zoom-in-down" data-aos-duration="2000"  class="flex flex-col">
                        <div class="mb-4">
                            <label for="name" class="block text-sm font-medium text-gray-700">Your Name</label>
                            <input type="text" id="name" v-model="form.name"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                        </div>

                        <div class="mb-4">
                            <label for="email" class="block text-sm font-medium text-gray-700">Your Email</label>
                            <input type="email" id="email" v-model="form.email"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                        </div>
                        <div class="mb-4">
                            <label for="comment" class="block text-sm font-medium text-gray-700">Your Comment</label>
                            <textarea id="comment" v-model="form.comment"
                                class="mt-1 block w-full h-[200px] px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"></textarea>
                        </div>

                        <button type="submit"
                            class="w-full bg-[#15b8a6] text-white py-2 px-4 rounded-md hover:bg-[#15b8a6]focus:outline-none focus:ring-2  focus:ring-offset-2">Send
                            Message</button>
                    </div>
                </form>
            </div>
        </div>

    </div>
</template>

<script>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

onMounted(() => {
    AOS.init();
});

    export default {
        data() {
            return {
                form: {
                    name: '',
                    email: '',
                    question: '',
                    comment: ''
                }
            };
        },
        methods: {
            submitForm() {
                // Handle form submission
                console.log('Form submitted:', this.form);
            }
        }
    };
   
</script>