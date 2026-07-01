<template>
  <section class="py-24 bg-slate-900 border-t border-white/5">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-16">
        <div class="max-w-2xl">
          <div class="inline-flex items-center gap-2 px-4 py-2 bg-white/5 border border-white/10 rounded-full mb-6">
            <span class="w-2 h-2 rounded-full bg-accent-500"></span>
            <span class="text-slate-300 text-xs font-bold uppercase tracking-wider">Latest Insights</span>
          </div>
          <h2 class="text-4xl md:text-5xl font-black text-white mb-6">News & Articles</h2>
          <p class="text-slate-400 text-lg">Stay updated with the latest trends in traffic technology, toll management, and infrastructure development.</p>
        </div>
        <NuxtLink to="/blogs" class="inline-flex items-center justify-center px-8 py-4 border border-white/10 text-sm font-bold rounded-full text-white bg-white/5 hover:bg-white/10 hover:border-white/20 backdrop-blur-sm transition-all duration-300 gap-3 group flex-shrink-0">
          View All Blogs
          <svg class="w-5 h-5 text-accent-500 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </NuxtLink>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <article v-for="blog in recentBlogs" :key="blog.id" class="bg-slate-950 rounded-3xl border border-white/5 overflow-hidden hover:border-accent-500/30 transition-all duration-500 group flex flex-col hover:shadow-2xl hover:shadow-accent-500/5">
          <NuxtLink :to="`/blogs/${blog.slug}`" class="block h-64 bg-slate-900 relative overflow-hidden">
            <!-- Decorative gradient fallback since we don't have guaranteed images -->
            <img v-if="blog.image" :src="blog.image" :alt="blog.title" class="absolute inset-0 w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 opacity-80 group-hover:opacity-100" />
            <div v-else class="absolute inset-0 bg-gradient-to-br from-slate-800 to-slate-900 group-hover:scale-105 transition-transform duration-700 flex items-center justify-center">
              <svg class="w-16 h-16 text-slate-700" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9a2 2 0 00-2-2h-2m-4-3H9M7 16h6M7 8h6v4H7V8z" />
              </svg>
            </div>
            <!-- Overlay -->
            <div class="absolute inset-0 bg-gradient-to-t from-slate-950 to-transparent opacity-60"></div>
            
            <div class="absolute top-6 left-6 px-4 py-1.5 bg-white/10 backdrop-blur-md text-white text-xs font-bold uppercase tracking-wider rounded-full border border-white/10 shadow-sm">
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
              <h3 class="text-2xl font-black text-white mb-4 line-clamp-2 leading-tight">{{ blog.title }}</h3>
            </NuxtLink>
            
            <p class="text-slate-400 text-base leading-relaxed mb-8 line-clamp-3 flex-1">
              {{ blog.excerpt }}
            </p>
            
            <NuxtLink :to="`/blogs/${blog.slug}`" class="inline-flex items-center text-sm font-bold text-white group-hover:text-accent-400 transition-colors mt-auto border-b border-transparent group-hover:border-accent-400 pb-1 self-start">
              Read Article
              <svg class="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
              </svg>
            </NuxtLink>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { blogs } from '~/data/blogs'

// Show only the first 3 blogs on the homepage
const recentBlogs = blogs.slice(0, 3)
</script>
