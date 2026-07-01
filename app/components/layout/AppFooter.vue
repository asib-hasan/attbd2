<template>
  <footer class="relative bg-[#051126] text-slate-400 border-t border-white/5 font-sans pt-20 pb-10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <!-- Top Section -->
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-10 lg:gap-8 text-sm mb-16">
        
        <!-- Column 1: About Us -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">About Us</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/about" class="footer-link">Company Overview</NuxtLink></li>
            <li><NuxtLink to="/about#mission" class="footer-link">Vision & Mission</NuxtLink></li>
            <li><NuxtLink to="/about#board" class="footer-link">Board of Directors</NuxtLink></li>
            <li><NuxtLink to="/contact" class="footer-link">Careers</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 2: Solutions -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Solutions</h3>
          <ul class="space-y-4">
            <li v-for="s in solutionLinks" :key="s.to">
              <NuxtLink :to="s.to" class="footer-link">{{ s.label }}</NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Column 3: Products -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Products</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/products/counters-classifiers" class="footer-link">Traffic Counters</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Toll Systems</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Weigh-in-Motion</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">LED Displays</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 4: Quick Links -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Quick Links</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/contact" class="footer-link">Contact Us</NuxtLink></li>
            <li><NuxtLink to="/blogs" class="footer-link">News & Events</NuxtLink></li>
            <li><NuxtLink to="/projects" class="footer-link">Our Projects</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 5: Brand & Social -->
        <div class="col-span-2 lg:col-span-1">
          <NuxtLink to="/" class="inline-block mb-6">
            <img src="/logo.png" alt="ATT Logo" class="h-14 lg:h-16 w-auto" />
          </NuxtLink>
          <p class="text-sm leading-relaxed mb-6 text-slate-400">
            Asian Traffic Technologies Ltd. Providing end-to-end infrastructure solutions for a modern Bangladesh.
          </p>
          <div class="flex items-center gap-3">
            <a href="#" aria-label="Facebook" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
            </a>
            <a href="#" aria-label="LinkedIn" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
          </div>
        </div>
      </div>
      
      <!-- Bottom Bar -->
      <div class="border-t border-white/10 pt-8 flex flex-col md:flex-row items-center justify-between gap-4 text-xs text-slate-500">
        <p>© {{ currentYear }} Asian Traffic Technologies Ltd. All Rights Reserved.</p>
        <p>
          Developed By <a href="https://creativetechpark.com/" target="_blank" rel="noopener noreferrer" class="text-blue-500 hover:text-blue-400 font-bold transition-colors">Creative Tech Park</a>
        </p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'

const currentYear = new Date().getFullYear()

const solutionLinks = solutions.slice(0, 4).map(s => ({
  to: `/solutions#${s.slug}`,
  label: s.title,
}))
</script>

<style scoped>
.footer-link {
  display: inline-block;
  font-size: 0.875rem;
  color: #94a3b8; /* slate-400 */
  transition: all 0.2s ease;
}
.footer-link:hover {
  color: #3b82f6; /* blue-500 */
  transform: translateX(2px);
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2.25rem;
  height: 2.25rem;
  border-radius: 50%;
  background: #0f172a; /* slate-900 */
  color: #94a3b8; /* slate-400 */
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.2s ease;
}
.social-icon:hover {
  background: #2563eb; /* blue-600 */
  color: #ffffff;
  border-color: #2563eb;
  transform: translateY(-2px);
}
</style>
