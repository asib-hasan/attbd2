<template>
  <main class="bg-slate-950 min-h-screen">
    <PageHero
      title="News & Insights"
      subtitle="Stay updated with our latest industry insights, company news, and technological advancements in the ITS sector."
      label="Our Blog"
    />

    <section class="py-24 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <article v-for="blog in blogs" :key="blog.id" class="bg-slate-900/50 backdrop-blur-md rounded-3xl border border-white/5 overflow-hidden hover:border-accent-500 hover:shadow-[0_0_30px_rgba(59,130,246,0.1)] transition-all duration-500 group flex flex-col">
            <NuxtLink :to="`/blogs/${blog.slug}`" class="block h-56 bg-slate-950 relative overflow-hidden border-b border-white/5">
              <img v-if="blog.image" :src="blog.image" :alt="blog.title" class="absolute inset-0 w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-out opacity-80 group-hover:opacity-100" />
              <div v-else class="absolute inset-0 bg-gradient-to-br from-slate-800 to-slate-900 group-hover:scale-105 transition-transform duration-700 ease-out flex items-center justify-center">
                <svg class="w-12 h-12 text-slate-700" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9a2 2 0 00-2-2h-2m-4-3H9M7 16h6M7 8h6v4H7V8z" />
                </svg>
              </div>
              <!-- Dark overlay -->
              <div class="absolute inset-0 bg-slate-950/20 group-hover:bg-slate-950/0 transition-colors duration-500"></div>

              <div class="absolute top-5 left-5 px-4 py-1.5 bg-white/10 backdrop-blur-md text-white text-[10px] font-bold uppercase tracking-widest rounded-full border border-white/10 shadow-sm">
                {{ blog.category }}
              </div>
            </NuxtLink>
            
            <div class="p-8 flex-1 flex flex-col">
              <div class="flex items-center gap-4 text-xs text-accent-500 mb-5 font-bold uppercase tracking-widest">
                <span class="flex items-center gap-2">
                  <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
                  {{ blog.date }}
                </span>
              </div>
              
              <NuxtLink :to="`/blogs/${blog.slug}`" class="block group-hover:text-accent-400 transition-colors">
                <h3 class="text-2xl font-black text-white mb-4 leading-tight">{{ blog.title }}</h3>
              </NuxtLink>
              
              <p class="text-slate-400 text-sm leading-relaxed mb-8 line-clamp-3 flex-1">
                {{ blog.excerpt }}
              </p>
              
              <NuxtLink :to="`/blogs/${blog.slug}`" class="inline-flex items-center text-xs font-bold text-slate-300 group-hover:text-accent-400 transition-colors group/link mt-auto uppercase tracking-widest pt-4 border-t border-white/5">
                Read Article
                <svg class="w-4 h-4 ml-2 group-hover/link:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
                </svg>
              </NuxtLink>
            </div>
          </article>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { blogs } from '~/data/blogs'

useSeoMeta({
  title: 'Blog & Insights — Asian Traffic Technologies Ltd',
  description: 'Read the latest news, technological insights, and company updates from Asian Traffic Technologies Ltd.',
})
</script>
