<template>
  <section class="py-24 bg-slate-50 border-t border-slate-200 overflow-hidden">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-16">
      <div class="text-center" v-animate="'animate-fade-up'">
        <h2 class="text-xl font-bold text-slate-500 uppercase tracking-widest border-b border-slate-300 pb-4 inline-block px-8">Trusted By</h2>
      </div>
    </div>
    
    <!-- Clients Slider -->
    <div class="relative w-full overflow-hidden group" v-animate="'animate-fade-in delay-200'">
      <!-- Gradient masks for smooth edges in light mode -->
      <div class="absolute inset-y-0 left-0 w-16 md:w-32 bg-gradient-to-r from-slate-50 to-transparent z-10 pointer-events-none"></div>
      <div class="absolute inset-y-0 right-0 w-16 md:w-32 bg-gradient-to-l from-slate-50 to-transparent z-10 pointer-events-none"></div>
      
      <div class="flex animate-marquee opacity-90 group-hover:opacity-100 transition-opacity duration-500 w-max hover:[animation-play-state:paused]">
        <!-- Duplicate lists for seamless loop -->
        <div v-for="n in 2" :key="n" class="flex gap-8 md:gap-12 items-center px-4 md:px-6 w-max">
          <div v-for="image in clientImages" :key="image + n" class="flex items-center justify-center transition-transform hover:scale-105 flex-shrink-0 cursor-pointer bg-white rounded-2xl shadow-lg border border-slate-100 p-4 h-24 w-40 md:h-28 md:w-48">
            <!-- Displaying the original logo inside a clean white box -->
            <img :src="`/Clients/${image}`" alt="Client Logo" class="max-h-full max-w-full object-contain" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const clientImages = [
  'one.PNG',
  'two.PNG',
  'three.PNG',
  'four.PNG',
  'five.PNG',
  'six.PNG',
  'seven.PNG',
  'eight.PNG',
  'nine.PNG',
  'ten.PNG'
]
</script>

<style scoped>
.animate-marquee {
  animation: marquee 40s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>
