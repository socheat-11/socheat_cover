<template>
    <div>
        <!-- Loading Screen -->
        <div v-if="loading" class="fixed inset-0 flex items-center justify-center bg-[#FFF]">
            <span class="loader"></span>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                loading: true, // Initial loading state
            };
        },
        mounted() {
            // Simulate loading time
            setTimeout(() => {
                this.loading = false; // Hide loading screen after 3 seconds
            }, 3000); // 3 seconds delay
        },
    };
</script>

<style scoped>
   .loader {
    position: relative;
    width: 85px;
    height: 50px;
    background-repeat: no-repeat;
    background-image: linear-gradient(#15b8a6 50px, transparent 0),
                      linear-gradient(#15b8a6 50px, transparent 0),
                      linear-gradient(#15b8a6 50px, transparent 0),
                      linear-gradient(#15b8a6 50px, transparent 0),
                      linear-gradient(#15b8a6 50px, transparent 0),
                      linear-gradient(#15b8a6 50px, transparent 0);
    background-position: 0px center, 15px center, 30px center, 45px center, 60px center, 75px center, 90px center;
    animation: rikSpikeRoll 0.65s linear infinite alternate;
  }
@keyframes rikSpikeRoll {
  0% { background-size: 10px 3px;}
  16% { background-size: 10px 50px, 10px 3px, 10px 3px, 10px 3px, 10px 3px, 10px 3px}
  33% { background-size: 10px 30px, 10px 50px, 10px 3px, 10px 3px, 10px 3px, 10px 3px}
  50% { background-size: 10px 10px, 10px 30px, 10px 50px, 10px 3px, 10px 3px, 10px 3px}
  66% { background-size: 10px 3px, 10px 10px, 10px 30px, 10px 50px, 10px 3px, 10px 3px}
  83% { background-size: 10px 3px, 10px 3px,  10px 10px, 10px 30px, 10px 50px, 10px 3px}
  100% { background-size: 10px 3px, 10px 3px, 10px 3px,  10px 10px, 10px 30px, 10px 50px}
}
    
</style>