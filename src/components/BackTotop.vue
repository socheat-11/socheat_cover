<template>
  <button
    v-show="showButton"
    @click="scrollToTop"
    class="fixed bottom-5 right-5 bg-[#f5fbfa] text-black hover:text-white h-12 w-12 rounded-full shadow-lg hover:bg-[#15b8a6] transition-all duration-300"
  >
    ↑
  </button>
</template>

<script>
export default {
  data() {
    return {
      showButton: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.showButton = window.scrollY > 200;
    },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
};
</script>
