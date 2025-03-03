<template>
  <div class="max-w-screen-xl mx-auto p-4" id="testimonial">
    <h2 class="text-3xl font-semibold text-center text-gray-800 mt-5">
      What Our Clients Say
    </h2>

    <div class="flex flex-wrap items-center justify-between px-4 py-2">
      <h1 class="text-[25px] text-[#000000] font-bold">
        <span class="relative inline-block">
          Services
          <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
        </span>
      </h1>

      <!-- Navigation Buttons -->
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

    <!-- Testimonials Section -->
    <div
      class="flex justify-center gap-4 mt-5"
      @mouseenter="stopAutoScroll"
      @mouseleave="startAutoScroll"
    >
      <div    
        v-for="(testimonial, index) in testimonialPairs"
        :key="index"
        class="bg-white shadow-[0px_0px_6px_2px_#edf2f7]  rounded-xl p-6 flex flex-col items-center w-full lg:w-1/2 transition-all duration-300"  data-aos="zoom-in-down" data-aos-duration="2000"
      >
        <img
          :src="testimonial.image"
          :alt="testimonial.author"
          class="w-20 h-20 rounded-full object-cover border-4 border-teal-500 shadow-md mb-4"
        />
        <div class="mt-4 flex space-y-3 flex-col items-center">
          <span class="font-semibold text-teal-600 text-lg">
            {{ testimonial.author }}
          </span>
          <span class="text-gray-500 text-sm">
            {{ testimonial.position }}
          </span>
        </div>
        <p class="text-gray-600 text-lg text-center italic">
          "{{ testimonial.text }}"
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed, onMounted, onUnmounted } from "vue";
import test1 from "../assets/test1.jpg";
import test2 from "../assets/test2.jpg";
import test3 from "../assets/test3.jpg";
import test4 from "../assets/test4.jpg";

export default {
  setup() {
    const testimonials = ref([
      { text: "The service was excellent! Highly recommend to anyone looking for quality work.",
        author: "John Doe", 
        position: "CEO, TechCorp", 
        image: test1 
      },
      { text: "Great experience, very professional and helpful.", 
        author: "Jane Smith", 
        position: "Manager, Global Inc.", 
        image: test2 
      },
      { text: "Amazing quality and top-notch support!", 
        author: "Alice Brown", 
        position: "Founder, Startup X", 
        image: test3 
      },
      { text: "Highly satisfied with the results, will work again!", 
        author: "Michael Green", 
        position: "CTO, Innovate Ltd.", 
        image: test4 
      },
      { text: "Great experience, very professional and helpful.", 
        author: "Jane Smith", 
        position: "Manager, Global Inc.", 
        image: test2 
      },
      { text: "Amazing quality and top-notch support!", 
        author: "Alice Brown", 
        position: "Founder, Startup X", 
        image: test3 
      },
    ]);

    const currentIndex = ref(0);
    const itemsPerRow = ref(window.innerWidth >= 1024 ? 3 : 1);
    let autoScrollInterval = null;

    const updateItemsPerRow = () => {
      itemsPerRow.value = window.innerWidth >= 1024 ? 2 : 1;
    };

    const testimonialPairs = computed(() => {
      return testimonials.value.slice(currentIndex.value, currentIndex.value + itemsPerRow.value);
    });

    const nextTestimonial = () => {
      currentIndex.value = (currentIndex.value + itemsPerRow.value) % testimonials.value.length;
    };

    const prevTestimonial = () => {
      currentIndex.value = (currentIndex.value - itemsPerRow.value + testimonials.value.length) % testimonials.value.length;
    };

    const startAutoScroll = () => {
      stopAutoScroll(); // Clear any existing interval before starting a new one
      autoScrollInterval = setInterval(() => {
        nextTestimonial();
      }, 5000); // Change every 5 seconds
    };

    const stopAutoScroll = () => {
      if (autoScrollInterval) {
        clearInterval(autoScrollInterval);
      }
    };

    onMounted(() => {
      window.addEventListener("resize", updateItemsPerRow);
      startAutoScroll();
    });

    onUnmounted(() => {
      stopAutoScroll();
      window.removeEventListener("resize", updateItemsPerRow);
    });

    return { testimonials, currentIndex, prevTestimonial, nextTestimonial, testimonialPairs, startAutoScroll, stopAutoScroll };
  },
};
</script>
