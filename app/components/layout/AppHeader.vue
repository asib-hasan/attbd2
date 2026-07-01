<template>
  <!-- Main Navigation -->
  <header class="absolute top-0 w-full z-50 transition-all duration-300 py-6">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between">

        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center gap-4 flex-shrink-0 group z-20">
          <img src="/logo.png" alt="ATT Logo" class="h-12 lg:h-16 w-auto opacity-100 transition-opacity" />
          <div class="hidden sm:block">
            <div class="font-black text-lg leading-tight text-white tracking-tight">
              ATT
            </div>
          </div>
        </NuxtLink>

        <!-- Desktop Nav (Pill Container) -->
        <nav class="hidden lg:flex items-center gap-2 border border-white/20 rounded-full px-2 py-1.5 bg-slate-900/40 backdrop-blur-md shadow-lg z-20 absolute left-1/2 -translate-x-1/2">
          <NuxtLink to="/" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Home</NuxtLink>
          <NuxtLink to="/about" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Solutions</NuxtLink>
          <NuxtLink to="/products" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Products</NuxtLink>
          <NuxtLink to="/services" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Services</NuxtLink>
          <NuxtLink to="/projects" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="px-4 py-2 rounded-full text-[10px] uppercase tracking-widest font-bold text-white hover:text-accent-400 transition-colors duration-300" active-class="!bg-slate-700/80 !text-white shadow-sm">Blog</NuxtLink>
        </nav>

        <div class="hidden lg:flex items-center z-20">
          <NuxtLink to="/contact" class="px-6 py-2.5 border border-accent-500 text-white text-[10px] uppercase tracking-widest font-bold rounded-full hover:bg-accent-500 hover:text-slate-900 transition-colors">
            Contact Us
          </NuxtLink>
        </div>

        <button
          class="lg:hidden p-2 rounded-lg transition-colors text-white z-20 hover:bg-white/10"
          @click="mobileOpen = !mobileOpen"
          aria-label="Toggle menu"
        >
          <svg v-if="!mobileOpen" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"/>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition name="dropdown">
      <div v-if="mobileOpen" class="lg:hidden bg-slate-950/95 backdrop-blur-md border-t border-white/10 shadow-2xl absolute w-full left-0 top-full">
        <div class="max-w-7xl mx-auto px-4 py-6 flex flex-col gap-2">
          <NuxtLink to="/" class="mobile-nav-link" @click="mobileOpen = false">Home</NuxtLink>
          <NuxtLink to="/about" class="mobile-nav-link" @click="mobileOpen = false">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="mobile-nav-link" @click="mobileOpen = false">Solutions</NuxtLink>
          <NuxtLink to="/products" class="mobile-nav-link" @click="mobileOpen = false">Products</NuxtLink>
          <NuxtLink to="/services" class="mobile-nav-link" @click="mobileOpen = false">Services</NuxtLink>
          <NuxtLink to="/projects" class="mobile-nav-link" @click="mobileOpen = false">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="mobile-nav-link" @click="mobileOpen = false">Blog</NuxtLink>
          <NuxtLink to="/contact" class="mt-4 px-6 py-3 border border-accent-500 text-white text-xs font-bold uppercase tracking-widest rounded-full text-center hover:bg-accent-500 hover:text-slate-900" @click="mobileOpen = false">Contact Us</NuxtLink>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const mobileOpen = ref(false)
const scrolled = ref(false)

const handleScroll = () => {
  scrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.dropdown-enter-active,
.dropdown-leave-active {
  transition: all 0.3s ease;
  transform-origin: top;
}
.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

.mobile-nav-link {
  display: block;
  padding: 0.75rem 1rem;
  font-size: 1rem;
  font-weight: 500;
  color: #cbd5e1;
  border-radius: 0.5rem;
  transition: all 0.2s;
}
.mobile-nav-link:hover {
  background: rgba(255, 255, 255, 0.05);
  color: white;
  padding-left: 1.25rem;
}
</style>
