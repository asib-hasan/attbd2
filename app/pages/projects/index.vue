<template>
  <main class="bg-slate-950 min-h-screen">
    <PageHero
      title="Our Projects"
      subtitle="A track record of successful ITS project delivery for government agencies and private sector clients across Bangladesh."
      label="Projects Portfolio"
    />

    <section class="py-24 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Filter tabs -->
        <div class="flex flex-wrap gap-4 mb-16 justify-center">
          <button
            v-for="cat in categories"
            :key="cat.key"
            :class="[
              'px-6 py-3 rounded-full text-sm font-bold uppercase tracking-widest transition-all duration-300 border backdrop-blur-md',
              activeCategory === cat.key
                ? 'bg-white/10 text-white border-white/20 shadow-[0_0_20px_rgba(255,255,255,0.05)]'
                : 'bg-slate-900/50 text-slate-400 border-white/5 hover:border-white/10 hover:text-white',
            ]"
            @click="activeCategory = cat.key"
          >
            {{ cat.label }}
            <span :class="['ml-2 text-xs font-medium', activeCategory === cat.key ? 'text-accent-400' : 'text-slate-500']">
              ({{ cat.key === 'all' ? projects.length : projects.filter(p => p.category === cat.key).length }})
            </span>
          </button>
        </div>

        <!-- Projects grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <NuxtLink
            v-for="project in filteredProjects"
            :key="project.slug"
            :to="`/projects/${project.slug}`"
            class="group bg-slate-900/50 backdrop-blur-md border border-white/5 hover:border-accent-500 hover:shadow-[0_0_30px_rgba(59,130,246,0.1)] transition-all duration-500 flex flex-col h-full relative overflow-hidden rounded-3xl"
          >
            <!-- Top accent line -->
            <div :class="['absolute top-0 left-0 w-full h-1 transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left duration-500 z-10', project.color || 'bg-gradient-to-r from-accent-500 to-blue-500']"></div>
            
            <div class="h-56 w-full bg-slate-950 relative overflow-hidden border-b border-white/5">
              <img :src="project.image || '/slider/hero_toll_collection.png'" :alt="project.title" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 ease-out" />
              <div class="absolute inset-0 bg-slate-950/40 group-hover:bg-slate-950/10 transition-colors duration-500"></div>
            </div>
            
            <div class="p-8 flex-1 flex flex-col">
              <div class="mb-5">
                <span class="text-[10px] font-bold uppercase tracking-widest px-3 py-1.5 bg-white/5 border border-white/10 rounded-full text-accent-500 inline-block">
                  {{ categoryLabel(project.category) }}
                </span>
              </div>
              
              <h3 class="text-xl font-black text-white mb-4 group-hover:text-accent-400 transition-colors uppercase tracking-wide leading-snug">{{ project.title }}</h3>
              <p class="text-sm text-slate-400 mb-8 flex-1 leading-relaxed">{{ project.shortDesc }}</p>
              
              <div class="pt-5 border-t border-white/5 flex flex-col gap-3 mt-auto">
                <div class="flex items-start justify-between text-xs font-bold text-slate-500 uppercase tracking-wider">
                  <span>Client:</span>
                  <span class="text-slate-300 text-right max-w-[60%] leading-tight">{{ project.client }}</span>
                </div>
                <div class="flex items-center justify-between text-xs font-bold text-slate-500 uppercase tracking-wider">
                  <span>Year:</span>
                  <span class="text-accent-500">{{ project.year }}</span>
                </div>
              </div>
            </div>
          </NuxtLink>
        </div>

        <!-- Empty state -->
        <div v-if="filteredProjects.length === 0" class="text-center py-24 text-slate-500">
          No projects found in this category.
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { projects, projectCategories } from '~/data/projects'

useSeoMeta({
  title: 'Projects — ATT | ITS Project Portfolio Bangladesh',
  description: 'Explore ATT\'s portfolio of completed and ongoing ITS projects across Bangladesh — toll systems, traffic monitoring, access control, and more.',
})

const route = useRoute()
const activeCategory = ref((route.query.cat as string) || 'all')

const categories = projectCategories

const filteredProjects = computed(() =>
  activeCategory.value === 'all'
    ? projects
    : projects.filter(p => p.category === activeCategory.value)
)

function categoryLabel(cat: string) {
  return projectCategories.find(c => c.key === cat)?.label ?? cat
}
</script>
