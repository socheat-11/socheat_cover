<template>
  <div class="max-w-screen-xl mx-auto p-4">
    <h2 class="text-3xl font-semibold text-center text-gray-800 mt-5">
      What Our Clients Say
    </h2>

    <div class="flex flex-wrap items-center justify-between px-4 py-2">
            <h1  class="text-[25px] text-[#000000] font-bold">
              <span class="relative inline-block">
                Services
                <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
              </span>
            </h1>
  
            <!-- Navigation -->
    <div class="mt-6 flex justify-center space-x-4">
      <button
        @click="prevTestimonial"
        class="w-10 h-10 bg-teal-500 text-white rounded-md flex items-center justify-center hover:bg-teal-600"
      >
        ❮
      </button>
      <button
        @click="nextTestimonial"
        class="w-10 h-10 bg-teal-500 text-white rounded-md flex items-center justify-center hover:bg-teal-600"
      >
        ❯
      </button>
    </div>
          </div>

    <div class="flex  justify-center gap-4 mt-5">
      <div
        v-for="(testimonial, index) in testimonialPairs"
        :key="index"
        class="bg-white shadow-lg rounded-xl p-6 flex flex-col items-center w-full lg:w-1/2"
      >
        <p class="text-gray-600 text-lg text-center italic">
          "{{ testimonial.text }}"
        </p>
        <div class="mt-4 flex flex-col items-center">
          <span class="font-semibold text-teal-600 text-lg">
            {{ testimonial.author }}
          </span>
          <span class="text-gray-500 text-sm">
            {{ testimonial.position }}
          </span>
        </div>
      </div>
    </div>

    
  </div>
</template>

<script>
import { ref, computed, onMounted } from "vue";

export default {
  setup() {
    const testimonials = ref([
      { text: "The service was excellent! Highly recommend to anyone looking for quality work.", author: "John Doe", position: "CEO, TechCorp" },
      { text: "Absolutely fantastic! The team went above and beyond my expectations.", author: "Sarah Smith", position: "Marketing Manager, XYZ Ltd." },
      { text: "Professional, timely, and great customer support. 10/10 experience!", author: "Michael Johnson", position: "CTO, Web Solutions" },
      { text: "Fast delivery and amazing support. Highly impressed!", author: "Emily Davis", position: "Founder, Startup X" },
      { text: "Great communication and attention to detail!", author: "James Brown", position: "Product Manager, SoftInc" },
      { text: "Will definitely work with them again. Superb service!", author: "Linda Green", position: "Operations Head, LogisticsPro" }
    ]);

    const currentIndex = ref(0);
    const itemsPerRow = ref(window.innerWidth >= 1024 ? 2 : 1); // 2 items for lg, 1 for sm

    // Update items per row on window resize
    const updateItemsPerRow = () => {
      itemsPerRow.value = window.innerWidth >= 1024 ? 2 : 1;
    };

    onMounted(() => {
      window.addEventListener("resize", updateItemsPerRow);
    });

    // Show testimonials dynamically based on screen size
    const testimonialPairs = computed(() => {
      return testimonials.value.slice(currentIndex.value, currentIndex.value + itemsPerRow.value);
    });

    const prevTestimonial = () => {
      currentIndex.value = (currentIndex.value - itemsPerRow.value + testimonials.value.length) % testimonials.value.length;
    };

    const nextTestimonial = () => {
      currentIndex.value = (currentIndex.value + itemsPerRow.value) % testimonials.value.length;
    };

    return { testimonials, currentIndex, prevTestimonial, nextTestimonial, testimonialPairs };
  },
};
</script>
