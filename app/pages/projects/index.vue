<template>
  <main class="bg-white min-h-screen">
    <PageHero
      title="Our Projects"
      subtitle="A track record of successful ITS project delivery for government agencies and private sector clients across Bangladesh."
      bgImage="/slider/bd_toll_plaza.png"
    />

    <section class="py-24 bg-slate-50 border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Filter tabs -->
        <div class="flex flex-wrap gap-4 mb-16 justify-center">
          <button
            v-for="cat in categories"
            :key="cat.key"
            :class="[
              'px-6 py-3 rounded-full text-sm font-bold uppercase tracking-widest transition-all duration-300 border',
              activeCategory === cat.key
                ? 'bg-blue-600 text-white border-blue-600 shadow-md shadow-blue-600/20'
                : 'bg-white text-slate-600 border-slate-200 hover:border-blue-200 hover:text-blue-600 hover:shadow-sm',
            ]"
            @click="activeCategory = cat.key"
          >
            {{ cat.label }}
            <span :class="['ml-2 text-xs font-medium', activeCategory === cat.key ? 'text-blue-200' : 'text-slate-400']">
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
            class="group bg-white border border-slate-200 hover:border-blue-200 hover:shadow-xl hover:shadow-blue-900/5 transition-all duration-500 flex flex-col h-full relative overflow-hidden rounded-3xl"
          >
            
            <div class="h-56 w-full bg-slate-100 relative overflow-hidden border-b border-slate-100">
              <img :src="project.image || '/slider/hero_toll_collection.png'" :alt="project.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700 ease-out" />
            </div>
            
            <div class="p-8 flex-1 flex flex-col relative">
              <div class="mb-5">
                <span class="text-[10px] font-bold uppercase tracking-widest px-3 py-1.5 bg-blue-50 border border-blue-100 rounded-full text-blue-700 inline-block">
                  {{ categoryLabel(project.category) }}
                </span>
              </div>
              
              <h3 class="text-xl font-bold text-slate-900 mb-4 group-hover:text-blue-600 transition-colors uppercase tracking-wide leading-snug">{{ project.title }}</h3>
              <p class="text-sm text-slate-600 mb-8 flex-1 leading-relaxed">{{ project.shortDesc }}</p>
              
              <div class="pt-5 border-t border-slate-100 flex flex-col gap-3 mt-auto">
                <div class="flex items-start justify-between text-xs font-bold text-slate-500 uppercase tracking-wider">
                  <span>Client:</span>
                  <span class="text-slate-800 text-right max-w-[60%] leading-tight">{{ project.client }}</span>
                </div>
                <div class="flex items-center justify-between text-xs font-bold text-slate-500 uppercase tracking-wider">
                  <span>Year:</span>
                  <span class="text-blue-600">{{ project.year }}</span>
                </div>
              </div>
              <!-- Standard Animated Bottom Border Line -->
              <div class="absolute bottom-0 left-0 h-[6px] bg-blue-600 w-0 group-hover:w-full transition-all duration-500 ease-out z-20"></div>
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
