<template>
    <div class="max-w-screen-xl mx-auto p-4" id="service">
        <div class="flex flex-col md:flex-row gap-4">
            <!-- Sidebar Buttons -->
            <div class="w-full md:w-1/3 ">
                <div data-aos="zoom-in-down" data-aos-duration="2000" class="mb-4 bg-white  rounded-md shadow-[0px_0px_6px_2px_#edf2f7] p-4 space-y-2">
                    <div  
                        v-for="(item, index) in items" 
                        :key="index" 
                        @click="selectedItem = item"
                        class="cursor-pointer p-3 rounded-md transition-all duration-300"
                        :class="selectedItem.id === item.id 
                          ? 'bg-[#15b8a6]  border border-[#15b8a6] text-white' 
                          : ' hover:text-[#15b8a6] '"
                    >
                        <h2 class="text-lg font-semibold">{{ item.title }}</h2>
                        <h3 class="text-sm mt-3">{{ item.subtitle }}</h3>
                        <p class="text-sm mt-3">{{ item.description }}</p>
                    </div>
                </div>
            </div>

            <!-- Contact Details -->
            <div class="w-full md:w-2/3  ">
                <div data-aos="zoom-in-down" data-aos-duration="2000" v-if="selectedItem" class="p-4 bg-white shadow-[0px_0px_6px_2px_#edf2f7] rounded-md">
                    <img :src="selectedItem.image" alt="Contact" class="w-full h-auto mb-4 rounded">
                    <h3 class="text-lg font-semibold mb-2">{{ selectedItem.title }}</h3>
                    <p>{{ selectedItem.description }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from "vue";

// Import images correctly (for static assets)
import img1 from "../assets/1.jpg";
import img2 from "../assets/2.jpg";

export default {
    setup() {
        // Define items
        const items = ref([
            {   id: 1, 
                title: "Step 1", 
                subtitle: "SEO Audit 1", 
                description: "We offer flexible and comprehensive online marketing plans 1", 
                image: img1 
            },
            {   id: 2, 
                title: "Step 2", 
                subtitle: "SEO Audit 2", 
                description: "We offer flexible and comprehensive online marketing plans 2", 
                image: img2 
            },
            {   id: 3, 
                title: "Step 3", 
                subtitle: "SEO Audit 3", 
                description: "We offer flexible and comprehensive online marketing plans 3", 
                image: img1 
            },
        ]);

        // Track selected item
        const selectedItem = ref(items.value[0]); // Default to first item

        return { items, selectedItem };
    }
};
</script>
