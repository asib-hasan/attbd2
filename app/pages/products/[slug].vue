<template>
  <main v-if="product" class="bg-slate-950 min-h-screen">
    <PageHero
      :title="product.title"
      :subtitle="product.shortDesc"
      label="Products"
      parent="Products"
      parent-to="/products"
    />

    <section class="py-20 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Back to List -->
        <NuxtLink to="/products" class="inline-flex items-center gap-2 text-sm font-bold text-slate-400 hover:text-white mb-12 transition-colors uppercase tracking-widest">
          <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"/></svg>
          Back to Products
        </NuxtLink>

        <div class="grid lg:grid-cols-12 gap-12 lg:gap-16 items-start">
          
          <!-- Image Column (Left Side) -->
          <div class="lg:col-span-5 lg:sticky lg:top-24 w-full aspect-[4/3] rounded-3xl overflow-hidden shadow-2xl border border-white/5 bg-white/5 flex items-center justify-center p-8 group">
            <img :src="product.image || '/product.png'" :alt="product.title" class="w-full h-full object-contain relative z-10 group-hover:scale-110 transition-transform duration-700 ease-out drop-shadow-2xl" />
          </div>

          <!-- Content Column (Right Side) -->
          <div class="lg:col-span-7">
            <!-- Title section -->
            <div class="mb-10 border-l-[4px] border-accent-500 pl-6">
              <div class="text-[10px] font-bold text-accent-500 uppercase tracking-widest mb-3">ATT Product</div>
              <h2 class="text-3xl md:text-5xl font-black text-white leading-tight uppercase tracking-wide">{{ product.title }}</h2>
            </div>

            <!-- Dynamic Content (from Summernote) -->
            <div v-if="product.content" class="prose prose-invert prose-slate max-w-none prose-lg mb-10" v-html="product.content"></div>

            <!-- Fallback for current static data -->
            <template v-else>
              <p class="text-slate-300 leading-relaxed text-lg mb-12">{{ product.description }}</p>

              <!-- Specs -->
              <div class="bg-slate-900/50 backdrop-blur-md border border-white/5 shadow-2xl rounded-3xl p-8 lg:p-10 mb-10">
                <h3 class="text-lg font-black text-white uppercase tracking-widest mb-8 flex items-center gap-3">
                  <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-accent-500">
                    <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"/><path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
                  </div>
                  Technical Specifications
                </h3>
                <div class="grid sm:grid-cols-2 gap-4">
                  <div v-for="spec in product.specs" :key="spec" class="flex items-start gap-4 bg-slate-950/50 p-5 rounded-2xl border border-white/5 hover:border-white/10 transition-colors">
                    <span class="text-sm text-slate-300 font-medium leading-relaxed">{{ spec }}</span>
                  </div>
                </div>
              </div>

              <!-- Applications -->
              <div class="bg-blue-900/10 border border-blue-500/20 rounded-3xl p-8 lg:p-10 backdrop-blur-md">
                <h3 class="text-lg font-black text-white uppercase tracking-widest mb-6 flex items-center gap-3">
                  Typical Applications
                </h3>
                <div class="flex flex-wrap gap-3">
                  <span v-for="app in product.applications" :key="app" class="px-5 py-2.5 bg-blue-500/10 text-blue-400 text-xs font-bold uppercase tracking-wider rounded-full border border-blue-500/20">
                    {{ app }}
                  </span>
                </div>
              </div>
            </template>
          </div>
        </div>
      </div>
    </section>
  </main>

  <main v-else class="min-h-screen flex items-center justify-center text-center px-4 bg-slate-950">
    <div>
      <div class="text-7xl font-black text-slate-800 mb-4 tracking-tighter">404</div>
      <h1 class="text-3xl font-bold text-white mb-4">Product Not Found</h1>
      <NuxtLink to="/products" class="px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 text-white font-bold rounded-full transition-all uppercase tracking-widest text-sm">
        Back to Products
      </NuxtLink>
    </div>
  </main>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'
import { products } from '~/data/products'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const product = computed(() => products.find(p => p.slug === slug.value))
const otherProducts = computed(() => products.filter(p => p.slug !== slug.value))
const iconComponent = computed(() => (icons as any)[product.value?.icon ?? 'Activity'] || icons.Activity)

useSeoMeta({
  title: computed(() => product.value ? `${product.value.title} — ATT Products` : 'Product Not Found'),
  description: computed(() => product.value?.shortDesc ?? ''),
})
</script>
