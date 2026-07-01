<template>
  <main v-if="project" class="bg-slate-950 min-h-screen">
    <PageHero
      :title="project.title"
      :subtitle="project.shortDesc"
      :label="categoryLabel"
      parent="Projects"
      parent-to="/projects"
    />

    <section class="py-24 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">
          <!-- Main -->
          <div class="lg:col-span-2">
            <!-- Meta bar -->
            <div class="flex flex-wrap items-center gap-5 mb-10 p-6 bg-slate-900/50 backdrop-blur-md rounded-3xl border border-white/5 shadow-2xl">
              <div class="flex items-center gap-3 text-sm">
                <svg class="w-5 h-5 text-accent-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"/></svg>
                <span class="text-slate-400">Client:</span>
                <span class="font-bold text-white">{{ project.client }}</span>
              </div>
              <div class="w-px h-6 bg-white/10 hidden sm:block"></div>
              <div class="flex items-center gap-3 text-sm">
                <svg class="w-5 h-5 text-accent-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5"/></svg>
                <span class="text-slate-400">Year:</span>
                <span class="font-bold text-white">{{ project.year }}</span>
              </div>
              <div class="w-px h-6 bg-white/10 hidden sm:block"></div>
              <span :class="['text-[10px] font-bold uppercase tracking-widest px-4 py-2 rounded-full border border-white/10 shadow-sm', categoryBadge]">
                {{ categoryLabel }}
              </span>
            </div>

            <!-- Title section -->
            <div class="mb-10 border-l-[4px] border-accent-500 pl-6">
              <div class="text-[10px] font-bold text-accent-500 uppercase tracking-widest mb-3">ATT Project Showcase</div>
              <h2 class="text-3xl md:text-4xl font-black text-white uppercase tracking-wide leading-tight">{{ project.title }}</h2>
            </div>
            
            <!-- Project Main Image -->
            <div class="w-full h-64 md:h-96 rounded-3xl overflow-hidden mb-12 border border-white/5 shadow-2xl relative group">
              <img :src="project.image || '/slider/hero_toll_collection.png'" :alt="project.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-out" />
              <div class="absolute inset-0 bg-slate-950/20 group-hover:bg-slate-950/0 transition-colors"></div>
            </div>

            <p class="text-slate-300 leading-relaxed text-lg mb-12">{{ project.description }}</p>

            <!-- Achievements -->
            <div class="bg-slate-900/50 backdrop-blur-md border border-white/5 rounded-3xl p-8 lg:p-10 shadow-2xl">
              <h3 class="text-xl font-black text-white uppercase tracking-widest mb-8 flex items-center gap-3">
                <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-accent-500">
                  <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                </div>
                Project Highlights & Scope
              </h3>
              <div class="grid sm:grid-cols-2 gap-4">
                <div v-for="achievement in project.achievements" :key="achievement" class="flex items-start gap-4 bg-slate-950/50 p-5 rounded-2xl border border-white/5 hover:border-white/10 transition-colors">
                  <span class="text-sm text-slate-300 font-medium leading-relaxed">{{ achievement }}</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Sidebar -->
          <div class="space-y-8">
            <div class="bg-slate-900 border border-white/10 rounded-3xl p-8 text-white relative overflow-hidden group">
              <!-- Decorative glow -->
              <div class="absolute -top-10 -right-10 w-40 h-40 bg-accent-500/20 blur-3xl rounded-full group-hover:bg-accent-500/30 transition-colors"></div>
              
              <h3 class="font-black text-2xl mb-4 relative z-10">Similar Project?</h3>
              <p class="text-slate-400 text-sm mb-8 leading-relaxed relative z-10">Talk to us about your requirements. We have the expertise to deliver state-of-the-art solutions.</p>
              <NuxtLink to="/contact" class="block text-center px-6 py-4 bg-white/10 hover:bg-white/20 border border-white/20 text-white font-bold rounded-full transition-all text-sm uppercase tracking-widest relative z-10">
                Start a Conversation
              </NuxtLink>
            </div>

            <!-- Other projects -->
            <div class="bg-slate-900/50 backdrop-blur-md rounded-3xl p-8 border border-white/5">
              <h4 class="font-black text-white mb-6 text-sm uppercase tracking-widest">Other Projects</h4>
              <div class="space-y-4">
                <NuxtLink
                  v-for="p in otherProjects.slice(0, 5)"
                  :key="p.slug"
                  :to="`/projects/${p.slug}`"
                  class="flex items-start gap-4 p-4 rounded-2xl hover:bg-white/5 border border-transparent hover:border-white/10 transition-all group"
                >
                  <svg class="w-4 h-4 text-slate-500 group-hover:text-accent-500 flex-shrink-0 mt-0.5 transition-colors" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/></svg>
                  <div>
                    <div class="text-sm text-slate-300 group-hover:text-white font-bold leading-snug transition-colors">{{ p.title }}</div>
                    <div class="text-xs text-slate-500 mt-1 uppercase tracking-wider font-semibold">{{ p.year }}</div>
                  </div>
                </NuxtLink>
              </div>
              <NuxtLink to="/projects" class="flex items-center gap-2 mt-6 text-xs font-bold text-accent-500 hover:text-white transition-colors uppercase tracking-widest">
                View all projects
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <main v-else class="min-h-screen flex items-center justify-center text-center px-4 bg-slate-950">
    <div>
      <div class="text-7xl font-black text-slate-800 mb-4 tracking-tighter">404</div>
      <h1 class="text-3xl font-bold text-white mb-4">Project Not Found</h1>
      <NuxtLink to="/projects" class="px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 text-white font-bold rounded-full transition-all uppercase tracking-widest text-sm">
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
    completed: 'bg-green-500/10 text-green-400',
    ongoing: 'bg-blue-500/10 text-blue-400',
    fisheries: 'bg-cyan-500/10 text-cyan-400',
  }
  return map[project.value?.category ?? ''] ?? 'bg-white/10 text-white'
})

useSeoMeta({
  title: computed(() => project.value ? `${project.value.title} — ATT Projects` : 'Project Not Found'),
  description: computed(() => project.value?.shortDesc ?? ''),
})
</script>
