<template>
  <!-- Main Navigation -->
  <header :class="[
    isHomePage ? 'fixed' : 'sticky',
    'top-0 w-full z-50 transition-all duration-300',
    (scrolled || !isHomePage) ? 'bg-white shadow-sm py-4 border-b border-slate-200' : 'bg-transparent py-6'
  ]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between">

        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center gap-3 flex-shrink-0 group z-20">
          <img src="/logo.png" alt="ATT Logo" class="h-10 lg:h-12 w-auto group-hover:scale-105 transition-transform duration-300" />
          <div :class="['hidden sm:block font-black text-2xl leading-none tracking-tight transition-colors', (scrolled || !isHomePage) ? 'text-slate-900' : 'text-white']">
            ATT
          </div>
        </NuxtLink>

        <!-- Desktop Nav -->
        <nav class="hidden lg:flex items-center gap-8 z-20">
          <NuxtLink to="/" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Home</NuxtLink>
          <NuxtLink to="/about" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Solutions</NuxtLink>
          <NuxtLink to="/products" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Products</NuxtLink>
          <NuxtLink to="/services" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Services</NuxtLink>
          <NuxtLink to="/projects" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="text-sm font-semibold transition-colors duration-300" :class="(scrolled || !isHomePage) ? 'text-slate-600 hover:text-blue-600' : 'text-white/90 hover:text-white'" active-class="!text-blue-600">Blog</NuxtLink>
        </nav>

        <div class="hidden lg:flex items-center z-20">
          <NuxtLink to="/contact" class="px-7 py-2.5 bg-blue-600 text-white text-sm font-bold rounded-lg hover:bg-blue-700 hover:shadow-lg hover:shadow-blue-600/30 transition-all transform hover:-translate-y-0.5">
            Contact Us
          </NuxtLink>
        </div>

        <button
          class="lg:hidden p-2 rounded-lg transition-colors text-slate-800 z-20 hover:bg-slate-100"
          @click="mobileOpen = !mobileOpen"
          aria-label="Toggle menu"
        >
          <svg v-if="!mobileOpen" class="w-6 h-6" :class="(scrolled || !isHomePage) ? 'text-slate-900' : 'text-white'" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"/>
          </svg>
          <svg v-else class="w-6 h-6" :class="(scrolled || !isHomePage) ? 'text-slate-900' : 'text-white'" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
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
          <NuxtLink to="/contact" class="mt-4 px-6 py-3 bg-blue-600 text-white text-sm font-bold rounded-lg text-center hover:bg-blue-700 transition-colors" @click="mobileOpen = false">Contact Us</NuxtLink>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const mobileOpen = ref(false)
const scrolled = ref(false)

// Check if we are on the homepage
const isHomePage = computed(() => route.path === '/')

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
