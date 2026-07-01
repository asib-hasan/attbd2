<template>
  <main v-if="solution" class="bg-slate-950 min-h-screen">
    <PageHero
      :title="solution.title"
      :subtitle="solution.shortDesc"
      label="Solutions"
      parent="Solutions"
      parent-to="/solutions"
    />

    <section class="py-20 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Back to List -->
        <NuxtLink to="/solutions" class="inline-flex items-center gap-2 text-sm font-bold text-slate-400 hover:text-white mb-12 transition-colors uppercase tracking-widest">
          <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"/></svg>
          Back to Solutions
        </NuxtLink>

        <div class="grid lg:grid-cols-12 gap-12 lg:gap-16 items-start">
          
          <!-- Image Column (Left Side) -->
          <div v-if="solution.image" class="lg:col-span-5 lg:sticky lg:top-24 w-full aspect-[4/3] rounded-3xl overflow-hidden shadow-2xl border border-white/10 group">
            <div class="absolute inset-0 bg-slate-950/20 group-hover:bg-transparent transition-colors duration-500 z-10"></div>
            <img :src="solution.image" :alt="solution.title" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          </div>

          <!-- Content Column (Right Side) -->
          <div :class="solution.image ? 'lg:col-span-7' : 'lg:col-span-12 max-w-4xl'">
            <!-- Icon + label -->
            <div class="flex items-center gap-5 mb-10">
              <div v-if="!solution.image" :class="['w-16 h-16 rounded-2xl bg-white/5 border border-white/10 flex items-center justify-center text-accent-500 shadow-lg flex-shrink-0']">
                <component :is="iconComponent" :size="32" />
              </div>
              <div>
                <div class="text-xs font-bold text-accent-500 uppercase tracking-widest mb-1">ATT Solution</div>
                <h2 class="text-3xl md:text-5xl font-black text-white">{{ solution.title }}</h2>
              </div>
            </div>

            <!-- Dynamic Content (from Summernote) -->
            <div v-if="solution.content" class="prose prose-invert prose-slate max-w-none prose-lg mb-10" v-html="solution.content"></div>

            <!-- Fallback for current static data -->
            <template v-else>
              <!-- Description -->
              <div class="prose prose-invert prose-slate max-w-none mb-10">
                <p class="text-slate-300 leading-relaxed text-lg">{{ solution.description }}</p>
              </div>

              <!-- Features -->
              <div class="bg-slate-900/50 backdrop-blur-md rounded-3xl p-8 lg:p-10 mb-10 border border-white/5 shadow-2xl">
                <h3 class="text-xl font-black text-white mb-8 flex items-center gap-3">
                  <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-accent-500">
                    <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                  </div>
                  Key Features & Capabilities
                </h3>
                <div class="grid sm:grid-cols-2 gap-4">
                  <div v-for="feature in solution.features" :key="feature" class="flex items-start gap-4 bg-slate-950/50 rounded-2xl p-5 border border-white/5 hover:border-white/10 transition-colors">
                    <svg class="w-5 h-5 text-accent-500 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5"/></svg>
                    <span class="text-sm text-slate-300 font-medium leading-relaxed">{{ feature }}</span>
                  </div>
                </div>
              </div>
            </template>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- 404 state -->
  <main v-else class="min-h-screen flex items-center justify-center text-center px-4 bg-slate-950">
    <div>
      <div class="text-7xl font-black text-slate-800 mb-4 tracking-tighter">404</div>
      <h1 class="text-3xl font-bold text-white mb-4">Solution Not Found</h1>
      <p class="text-slate-400 mb-8">The solution you're looking for doesn't exist.</p>
      <NuxtLink to="/solutions" class="px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 text-white font-bold rounded-full transition-all uppercase tracking-widest text-sm">
        Back to Solutions
      </NuxtLink>
    </div>
  </main>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'
import { solutions } from '~/data/solutions'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const solution = computed(() => solutions.find(s => s.slug === slug.value))
const otherSolutions = computed(() => solutions.filter(s => s.slug !== slug.value))
const iconComponent = computed(() => (icons as any)[solution.value?.icon ?? 'Activity'] || icons.Activity)

useSeoMeta({
  title: computed(() => solution.value ? `${solution.value.title} — ATT Solutions` : 'Solution Not Found'),
  description: computed(() => solution.value?.shortDesc ?? ''),
})

// 404 if not found
if (!solution.value && import.meta.server) {
  throw createError({ statusCode: 404, message: 'Solution not found' })
}
</script>
