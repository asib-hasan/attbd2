<template>
  <main v-if="project" class="bg-white min-h-screen">
    <PageHero
      :title="project.title"
      :subtitle="project.shortDesc"
      :label="categoryLabel"
      parent="Projects"
      parent-to="/projects"
      :bgImage="project.image || '/slider/hero_toll_collection.png'"
    />

    <section class="py-24 bg-slate-50 border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">
          <!-- Main -->
          <div class="lg:col-span-2">
            <!-- Meta bar -->
            <div class="flex flex-wrap items-center gap-5 mb-10 p-6 bg-white rounded-3xl border border-slate-200 shadow-xl">
              <div class="flex items-center gap-3 text-sm">
                <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"/></svg>
                <span class="text-slate-500">Client:</span>
                <span class="font-bold text-slate-900">{{ project.client }}</span>
              </div>
              <div class="w-px h-6 bg-slate-200 hidden sm:block"></div>
              <div class="flex items-center gap-3 text-sm">
                <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5"/></svg>
                <span class="text-slate-500">Year:</span>
                <span class="font-bold text-slate-900">{{ project.year }}</span>
              </div>
              <div class="w-px h-6 bg-slate-200 hidden sm:block"></div>
              <span :class="['text-[10px] font-bold uppercase tracking-widest px-4 py-2 rounded-full border shadow-sm', categoryBadge]">
                {{ categoryLabel }}
              </span>
            </div>

            <!-- Title section -->
            <div class="mb-10 border-l-[4px] border-blue-600 pl-6">
              <div class="text-[10px] font-bold text-blue-600 uppercase tracking-widest mb-3">ATT Project Showcase</div>
              <h2 class="text-3xl md:text-4xl font-black text-slate-900 uppercase tracking-wide leading-tight">{{ project.title }}</h2>
            </div>
            
            <!-- Project Main Image -->
            <div class="w-full h-64 md:h-96 rounded-3xl overflow-hidden mb-12 border border-slate-200 shadow-xl relative group bg-white">
              <img :src="project.image || '/slider/hero_toll_collection.png'" :alt="project.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-out" />
            </div>

            <p class="text-slate-600 leading-relaxed text-lg mb-12">{{ project.description }}</p>

            <!-- Achievements -->
            <div class="bg-white border border-slate-200 rounded-3xl p-8 lg:p-10 shadow-xl">
              <h3 class="text-xl font-black text-slate-900 uppercase tracking-widest mb-8 flex items-center gap-3">
                <div class="w-8 h-8 rounded-full bg-blue-50 flex items-center justify-center text-blue-600">
                  <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                </div>
                Project Highlights & Scope
              </h3>
              <div class="grid sm:grid-cols-2 gap-4">
                <div v-for="achievement in project.achievements" :key="achievement" class="flex items-start gap-4 bg-slate-50 p-5 rounded-2xl border border-slate-100 hover:border-blue-200 transition-colors shadow-sm">
                  <span class="text-sm text-slate-700 font-medium leading-relaxed">{{ achievement }}</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Sidebar -->
          <div class="space-y-8">
            <div class="bg-blue-600 border border-blue-700 rounded-3xl p-8 text-white relative overflow-hidden group shadow-xl">
              <!-- Decorative glow -->
              <div class="absolute -top-10 -right-10 w-40 h-40 bg-white/20 blur-3xl rounded-full group-hover:bg-white/30 transition-colors"></div>
              
              <h3 class="font-black text-2xl mb-4 relative z-10">Similar Project?</h3>
              <p class="text-blue-100 text-sm mb-8 leading-relaxed relative z-10">Talk to us about your requirements. We have the expertise to deliver state-of-the-art solutions.</p>
              <NuxtLink to="/contact" class="block text-center px-6 py-4 bg-white text-blue-600 hover:bg-blue-50 font-bold rounded-full transition-all text-sm uppercase tracking-widest relative z-10 shadow-md">
                Start a Conversation
              </NuxtLink>
            </div>

            <!-- Other projects -->
            <div class="bg-white rounded-3xl p-8 border border-slate-200 shadow-xl">
              <h4 class="font-black text-slate-900 mb-6 text-sm uppercase tracking-widest">Other Projects</h4>
              <div class="space-y-4">
                <NuxtLink
                  v-for="p in otherProjects.slice(0, 5)"
                  :key="p.slug"
                  :to="`/projects/${p.slug}`"
                  class="flex items-start gap-4 p-4 rounded-2xl bg-slate-50 hover:bg-blue-50 border border-slate-100 hover:border-blue-200 transition-all group"
                >
                  <svg class="w-4 h-4 text-slate-400 group-hover:text-blue-600 flex-shrink-0 mt-0.5 transition-colors" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/></svg>
                  <div>
                    <div class="text-sm text-slate-700 group-hover:text-blue-700 font-bold leading-snug transition-colors">{{ p.title }}</div>
                    <div class="text-xs text-slate-500 mt-1 uppercase tracking-wider font-semibold">{{ p.year }}</div>
                  </div>
                </NuxtLink>
              </div>
              <NuxtLink to="/projects" class="flex items-center gap-2 mt-6 text-xs font-bold text-blue-600 hover:text-blue-700 transition-colors uppercase tracking-widest">
                View all projects
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <main v-else class="min-h-screen flex items-center justify-center text-center px-4 bg-slate-50">
    <div>
      <div class="text-7xl font-black text-slate-300 mb-4 tracking-tighter">404</div>
      <h1 class="text-3xl font-bold text-slate-900 mb-4">Project Not Found</h1>
      <NuxtLink to="/projects" class="px-8 py-4 bg-blue-600 hover:bg-blue-700 shadow-md border-transparent text-white font-bold rounded-full transition-all uppercase tracking-widest text-sm inline-block">
        Back to Projects
      </NuxtLink>
    </div>
  </main>
</template>

<script setup lang="ts">
import { projects, projectCategories } from '~/data/projects'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const project = computed(() => projects.find(p => p.slug === slug.value))
const otherProjects = computed(() => projects.filter(p => p.slug !== slug.value))

const categoryLabel = computed(() =>
  projectCategories.find(c => c.key === project.value?.category)?.label ?? 'Project'
)

const categoryBadge = computed(() => {
  const map: Record<string, string> = {
    completed: 'bg-green-50 border-green-200 text-green-700',
    ongoing: 'bg-blue-50 border-blue-200 text-blue-700',
    fisheries: 'bg-cyan-50 border-cyan-200 text-cyan-700',
  }
  return map[project.value?.category ?? ''] ?? 'bg-slate-50 border-slate-200 text-slate-700'
})

useSeoMeta({
  title: computed(() => project.value ? `${project.value.title} — ATT Projects` : 'Project Not Found'),
  description: computed(() => project.value?.shortDesc ?? ''),
})
</script>
