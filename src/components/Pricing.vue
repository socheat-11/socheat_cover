<template>
    <div class="bg-[#f5fbfa] mt-5">
        <section class="max-w-screen-xl mx-auto p-4 py-10" id="pricing">
            <div class="flex flex-wrap items-center justify-between px-4 py-2">
                <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
                    <span class="relative inline-block">
                        Pricing
                        <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
                    </span>
                </h1>

                <button
                    class="text-[#15b8a6] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
                    <span class="relative z-0">Hire Me</span>
                </button>
            </div>

            <div data-aos="zoom-in-down" data-aos-duration="2000" class="grid mt-5 grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
                <!-- Loop Through Plans -->
                <div  v-for="(plan, index) in pricingPlans" :key="index"
                    :class="['bg-white p-4 rounded-lg shadow-md', plan.featured ? 'border-t-4 border-[#15b8a6] text-start' : 'text-start']">
                    
                    <h3 class="text-xl font-bold">{{ plan.name }}</h3>
                    <p class="text-[50px] font-bold mt-2">
                        <span class="text-base relative -top-6 font-normal">$</span>{{ plan.price }}
                        <span class="text-base font-normal">/mo</span>
                    </p>

                    <ul class="mt-4 space-y-2 text-start text-gray-600">
                        <li v-for="(benefit, i) in plan.benefits" :key="i">
                            <FontAwesomeIcon class="text-[15px] text-[#15b8a6]" :icon="faCircleCheck" />
                            {{ benefit }}
                        </li>
                    </ul>

                    <button class="mt-6 w-full py-2 rounded-lg font-semibold"
                        :class="plan.featured ? 'hover:bg-[#f5fbfa] hover:text-[#15b8a6] bg-[#15b8a6] text-[#ffff]' 
                        : 'bg-[#f5fbfa] text-[#15b8a6] hover:bg-[#15b8a6] hover:text-[#ffff]'">
                        {{ plan.buttonText }}
                    </button>

                    <p v-if="plan.terms" class="text-xs text-gray-500 mt-2">*T&C Apply</p>
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
import { faCircleCheck } from '@fortawesome/free-solid-svg-icons';

onMounted(() => {
    AOS.init();
});

// Define Pricing Plans
const pricingPlans = [
    {
        name: "Free",
        price: 0,
        benefits: ["We offer a free month of service for new customers."],
        buttonText: "Free Demo",
        featured: false
    },
    {
        name: "Single",
        price: 9,
        benefits: [
            "We offer a free month of service for new customers.",
            "Access to limited features."
        ],
        buttonText: "Free Demo",
        featured: false
    },
    {
        name: "Professional",
        price: 49,
        benefits: [
            "We offer a free month of service for new customers.",
            "Priority customer support.",
            "Advanced analytics & reports.",
            "Unlimited access to premium features.",
            "Custom integrations."
        ],
        buttonText: "Buy Now",
        featured: true,
        terms: true
    },
    {
        name: "Enterprise",
        price: 99,
        benefits: [
            "Dedicated account manager.",
            "24/7 priority support.",
            "Tailored solutions for large businesses."
        ],
        buttonText: "Get Quote",
        featured: false
    }
];
</script>
