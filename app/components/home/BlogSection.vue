<template>
  <section class="py-24 bg-slate-50 border-t border-slate-200">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-16">
        <div class="max-w-2xl">
          <div class="inline-flex items-center gap-2 px-4 py-2 bg-blue-50 border border-blue-100 rounded-full mb-6">
            <span class="w-2 h-2 rounded-full bg-blue-600"></span>
            <span class="text-blue-700 text-xs font-bold uppercase tracking-wider">Latest Insights</span>
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">News & Articles</h2>
          <p class="text-slate-600 text-lg">Stay updated with the latest trends in traffic technology, toll management, and infrastructure development.</p>
        </div>
        <NuxtLink to="/blogs" class="inline-flex items-center justify-center px-8 py-4 border border-slate-200 text-sm font-bold rounded-full text-slate-700 bg-white hover:bg-blue-50 hover:border-blue-200 hover:text-blue-600 transition-all duration-300 gap-3 group flex-shrink-0">
          View All Blogs
          <svg class="w-5 h-5 text-blue-600 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </NuxtLink>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <article v-for="blog in recentBlogs" :key="blog.id" class="bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-blue-200 hover:shadow-xl hover:shadow-blue-900/5 transition-all duration-500 group flex flex-col relative">
          <NuxtLink :to="`/blogs/${blog.slug}`" class="block h-56 relative overflow-hidden bg-slate-100 border-b border-slate-100">
            <img v-if="blog.image" :src="blog.image" :alt="blog.title" class="absolute inset-0 w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-out" />
            <div v-else class="absolute inset-0 flex items-center justify-center group-hover:scale-105 transition-transform duration-700 ease-out">
              <svg class="w-12 h-12 text-slate-300" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9a2 2 0 00-2-2h-2m-4-3H9M7 16h6M7 8h6v4H7V8z" />
              </svg>
            </div>
            
            <div class="absolute top-5 left-5 px-4 py-1.5 bg-blue-600 text-white text-[10px] font-bold uppercase tracking-widest rounded-full shadow-md">
              {{ blog.category }}
            </div>
          </NuxtLink>
          
          <div class="p-8 flex-1 flex flex-col bg-white relative z-10">
            <div class="flex items-center gap-4 text-xs text-blue-600 mb-5 font-bold uppercase tracking-widest">
              <span class="flex items-center gap-2">
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
                {{ blog.date }}
              </span>
            </div>
            
            <NuxtLink :to="`/blogs/${blog.slug}`" class="block group-hover:text-blue-600 transition-colors">
              <h3 class="text-2xl font-bold text-slate-900 mb-4 leading-tight">{{ blog.title }}</h3>
            </NuxtLink>
            
            <p class="text-slate-600 text-sm leading-relaxed mb-8 line-clamp-3 flex-1">
              {{ blog.excerpt }}
            </p>
            
            <NuxtLink :to="`/blogs/${blog.slug}`" class="inline-flex items-center text-xs font-bold text-slate-500 group-hover:text-blue-600 transition-colors group/link mt-auto uppercase tracking-widest pt-5 border-t border-slate-100">
              Read Article
              <svg class="w-4 h-4 ml-2 group-hover/link:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
              </svg>
            </NuxtLink>
          </div>

          <!-- Standard Animated Bottom Border Line -->
          <div class="absolute bottom-0 left-0 h-[6px] bg-blue-600 w-0 group-hover:w-full transition-all duration-500 ease-out z-20 pointer-events-none"></div>
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
