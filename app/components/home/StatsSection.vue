<template>
  <section class="py-24 bg-slate-900 border-t border-white/5">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Left: Stats -->
        <div class="grid grid-cols-2 gap-6">
          <div
            v-for="(stat, index) in stats"
            :key="stat.label"
            v-animate="`animate-fade-up delay-${index * 100}`"
            class="bg-slate-950/50 backdrop-blur-sm border border-white/5 rounded-2xl p-8 text-center relative overflow-hidden group hover:bg-slate-800 transition-colors duration-500"
          >
            <div class="absolute inset-0 bg-gradient-to-br from-white/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity"></div>
            <div class="text-5xl font-black mb-3 text-white">
              <AnimatedCounter :value="stat.value" :suffix="stat.suffix" />
            </div>
            <div class="text-sm font-bold text-accent-500 uppercase tracking-widest">{{ stat.label }}</div>
            <div class="text-xs text-slate-500 mt-2">{{ stat.sub }}</div>
          </div>
        </div>

        <!-- Right: Why ATT -->
        <div>
          <div v-animate="'animate-fade-up'" class="inline-flex items-center gap-2 px-4 py-2 bg-white/5 border border-white/10 rounded-full mb-6">
            <span class="w-2 h-2 rounded-full bg-accent-500"></span>
            <span class="text-slate-300 text-xs font-bold uppercase tracking-wider">Why Choose ATT</span>
          </div>
          <h2 v-animate="'animate-fade-up delay-100'" class="text-4xl md:text-5xl font-black text-white mb-6 leading-tight">
            The Trusted Partner for <span class="text-transparent bg-clip-text bg-gradient-to-r from-accent-400 to-blue-400">Infrastructure</span>
          </h2>
          <p v-animate="'animate-fade-up delay-200'" class="text-slate-400 text-lg leading-relaxed mb-10">
            With over 25 years of experience, ATT combines deep local knowledge with world-class technology partnerships to deliver ITS solutions that work reliably in Bangladesh's challenging environment.
          </p>

          <div class="space-y-6">
            <div v-for="(point, index) in points" :key="point.title" v-animate="`animate-fade-up delay-${(index + 3) * 100}`" class="flex items-start gap-5 group">
              <div class="w-12 h-12 rounded-xl bg-slate-950 flex items-center justify-center flex-shrink-0 border border-white/10 group-hover:border-accent-500/50 transition-colors">
                <svg class="w-6 h-6 text-accent-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" :d="point.icon" />
                </svg>
              </div>
              <div>
                <div class="font-bold text-lg text-white mb-1 group-hover:text-accent-400 transition-colors">{{ point.title }}</div>
                <div class="text-base text-slate-500 leading-relaxed">{{ point.text }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import AnimatedCounter from '../common/AnimatedCounter.vue'

const stats = [
  { value: 25, suffix: '+', label: 'Years Experience', sub: 'Since 1999' },
  { value: 100, suffix: '+', label: 'Projects Delivered', sub: 'Nationwide' },
  { value: 50, suffix: '+', label: 'Clients Served', sub: 'Govt & Private' },
  { value: 8, suffix: '', label: 'Core Solutions', sub: 'ITS Domains' },
]

const points = [
  {
    title: 'End-to-End Project Delivery',
    text: 'From initial design and procurement through installation, commissioning, and long-term maintenance.',
    icon: 'M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
  },
  {
    title: 'Certified Local Expertise',
    text: 'Our teams are certified and trained on all major ITS platforms with decades of Bangladesh-specific experience.',
    icon: 'M4.26 10.147a60.436 60.436 0 00-.491 6.347A48.627 48.627 0 0112 20.904a48.627 48.627 0 018.232-4.41 60.46 60.46 0 00-.491-6.347m-15.482 0a50.57 50.57 0 00-2.658-.813A59.905 59.905 0 0112 3.493a59.902 59.902 0 0110.399 5.84c-.896.248-1.783.52-2.658.814m-15.482 0A50.697 50.697 0 0112 13.489a50.702 50.702 0 017.74-3.342M6.75 15a.75.75 0 100-1.5.75.75 0 000 1.5zm0 0v-3.675A55.378 55.378 0 0112 8.443m-7.007 11.55A5.981 5.981 0 006.75 15.75v-1.5',
  },
  {
    title: '24/7 Support & Maintenance',
    text: 'Round-the-clock emergency support and preventive maintenance contracts to maximize system uptime.',
    icon: 'M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z',
  },
]
</script>
