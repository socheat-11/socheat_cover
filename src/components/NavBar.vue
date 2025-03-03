<template>
  <nav class="bg-[#f5fbfa]">
    <div class="max-w-screen-xl flex  flex-wrap items-center justify-between mx-auto p-4">
      <a href="/home" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="../assets/logo.png" alt="Logo" class="h-8" />
      </a>
      <button
        @click="toggleMenu"
        type="button"
        class="inline-flex items-center p-2 w-8 h-8 justify-center text-sm text-[#a1ded4] rounded-lg md:hidden focus:outline-none focus:ring-2 focus:ring-gray-200 transition-all duration-300 transform hover:scale-110"
        aria-controls="navbar-default"
        :aria-expanded="isMenuOpen ? 'true' : 'false'"
        aria-label="Toggle navigation"
      >
        <span class="sr-only">Open main menu</span>
        <svg v-if="!isMenuOpen" class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15" />
        </svg>
        <svg v-else class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
      <div :class="isMenuOpen ? 'block' : 'hidden md:block'" class="w-full md:w-auto transition-all duration-300 ease-in-out" id="navbar-default">
        <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-[#a1ded4] lg:px-10 lg:rounded-full lg:border-2 rounded-lg md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0">
          <li v-for="item in menuItems" :key="item.name">
            <a :href="item.href" class="block py-3 px-3 text-black uppercase text-[12px] font-normal hover:text-[#15b8a6] transition-all duration-300 transform hover:scale-110">
              {{ item.name }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { name: 'Home', href: '#hero' },
        { name: 'About', href: '#about' },
        { name: 'Services', href: '#service' },
        { name: 'Testimonial', href: '#testimonial' },
        { name: 'Pricing', href: '#pricing' },
        { name: 'Blog', href: '#blog' }, // Capitalized "Blog"
        { name: 'Contact Us', href: '#contact' },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>
