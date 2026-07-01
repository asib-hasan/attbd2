<template>
  <main v-if="blog" class="bg-white min-h-screen pb-24">
    <!-- Hero Background Header -->
    <div class="relative w-full max-w-[1920px] mx-auto h-[400px] lg:h-[500px] flex items-center justify-center overflow-hidden border-b border-slate-200">
      <!-- Background Image -->
      <div class="absolute inset-0 z-0 bg-slate-900">
        <img v-if="blog.image" :src="blog.image" :alt="blog.title" class="w-full h-full object-cover scale-105" />
        <div v-else class="w-full h-full bg-gradient-to-br from-blue-900 to-slate-900"></div>
        <!-- Dark Blue Overlay for readable white text -->
        <div class="absolute inset-0 bg-blue-950/60 backdrop-blur-sm"></div>
      </div>

      <!-- Top Left Back Button -->
      <div class="absolute top-8 left-4 sm:left-6 lg:left-8 z-20">
        <NuxtLink to="/blogs" class="inline-flex items-center text-xs font-bold text-slate-300 hover:text-white transition-colors group uppercase tracking-widest drop-shadow-md">
          <svg class="w-4 h-4 mr-2 group-hover:-translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M7 16l-4-4m0 0l4-4m-4 4h18" />
          </svg>
          Back to all blogs
        </NuxtLink>
      </div>

      <!-- Header Content -->
      <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center mt-6">
        <div class="mb-6">
          <span class="inline-flex items-center gap-2 px-4 py-1.5 bg-blue-600 text-white text-[10px] font-bold uppercase tracking-widest rounded-full shadow-lg">
            {{ blog.category }}
          </span>
        </div>
        
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-black text-white mb-8 leading-tight drop-shadow-xl">
          {{ blog.title }}
        </h1>
        
        <div class="flex items-center justify-center gap-6 text-sm text-blue-100 font-bold uppercase tracking-widest drop-shadow-sm">
          <span class="flex items-center gap-2">
            <svg class="w-5 h-5 text-blue-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
            {{ blog.date }}
          </span>
        </div>
      </div>
    </div>

    <!-- Blog Content -->
    <article class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8 mt-16">
      <div class="prose prose-lg prose-slate max-w-none prose-headings:font-black prose-headings:text-slate-900 prose-p:text-slate-700 prose-a:text-blue-600 hover:prose-a:text-blue-500 mx-auto" v-html="blog.content"></div>
    </article>
  </main>
</template>

<script setup lang="ts">
import { blogs } from '~/data/blogs'

const route = useRoute()
const blog = computed(() => blogs.find(b => b.slug === route.params.slug))

if (!blog.value) {
  throw createError({ statusCode: 404, statusMessage: 'Blog not found', fatal: true })
}

useSeoMeta({
  title: () => `${blog.value?.title} — ATT Blog`,
  description: () => blog.value?.excerpt,
})
</script>
