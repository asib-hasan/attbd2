<template>
  <!-- Main Navigation -->
  <header :class="['fixed top-0 w-full z-50 transition-all duration-500', scrolled ? 'bg-white/80 backdrop-blur-xl shadow-[0_4px_30px_rgb(0,0,0,0.03)] py-3 border-b border-white/20' : 'bg-transparent py-6']">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between">

        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center gap-3 flex-shrink-0 group z-20">
          <img src="/logo.png" alt="ATT Logo" class="h-10 lg:h-12 w-auto group-hover:scale-105 transition-transform duration-300" />
          <div :class="['hidden sm:block font-black text-xl leading-none tracking-tight transition-colors', scrolled ? 'text-slate-900' : 'text-white']">
            ATT
          </div>
        </NuxtLink>

        <!-- Desktop Nav -->
        <nav class="hidden lg:flex items-center gap-1 z-20 bg-white/50 backdrop-blur-md px-2 py-1.5 rounded-full border border-slate-200/50 shadow-sm">
          <NuxtLink to="/" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Home</NuxtLink>
          <NuxtLink to="/about" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Solutions</NuxtLink>
          <NuxtLink to="/products" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Products</NuxtLink>
          <NuxtLink to="/services" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Services</NuxtLink>
          <NuxtLink to="/projects" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="px-4 py-2 text-sm font-semibold text-slate-700 hover:text-blue-600 hover:bg-white rounded-full transition-all duration-300" active-class="!text-blue-600 bg-white shadow-sm">Blog</NuxtLink>
        </nav>

        <div class="hidden lg:flex items-center z-20">
          <NuxtLink to="/contact" class="px-7 py-2.5 bg-slate-900 text-white text-sm font-bold rounded-full hover:bg-blue-600 hover:shadow-lg hover:shadow-blue-500/30 transition-all transform hover:-translate-y-0.5">
            Get a Quote
          </NuxtLink>
        </div>

        <button
          class="lg:hidden p-2 rounded-lg transition-colors text-slate-800 z-20 hover:bg-slate-100"
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
      <div v-if="mobileOpen" class="lg:hidden bg-white border-t border-slate-100 shadow-xl absolute w-full left-0 top-full">
        <div class="max-w-7xl mx-auto px-4 py-4 flex flex-col gap-1">
          <NuxtLink to="/" class="mobile-nav-link" @click="mobileOpen = false">Home</NuxtLink>
          <NuxtLink to="/about" class="mobile-nav-link" @click="mobileOpen = false">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="mobile-nav-link" @click="mobileOpen = false">Solutions</NuxtLink>
          <NuxtLink to="/products" class="mobile-nav-link" @click="mobileOpen = false">Products</NuxtLink>
          <NuxtLink to="/services" class="mobile-nav-link" @click="mobileOpen = false">Services</NuxtLink>
          <NuxtLink to="/projects" class="mobile-nav-link" @click="mobileOpen = false">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="mobile-nav-link" @click="mobileOpen = false">Blog</NuxtLink>
          <NuxtLink to="/contact" class="mt-4 px-6 py-3 bg-slate-900 text-white text-sm font-bold rounded-full text-center hover:bg-blue-600 transition-colors" @click="mobileOpen = false">Get a Quote</NuxtLink>
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
  color: #475569;
  border-radius: 0.5rem;
  transition: all 0.2s;
}
.mobile-nav-link:hover {
  background: #f1f5f9;
  color: #2563eb;
  padding-left: 1.25rem;
}
</style>
