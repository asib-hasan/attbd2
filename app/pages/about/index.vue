<template>
  <main class="bg-white min-h-screen font-sans">
    <PageHero
      title="About Us"
      subtitle="Bangladesh's leading Intelligent Transportation Systems provider — over 25 years of excellence in toll collection, traffic monitoring, and infrastructure technology."
      bgImage="/slider/realistic_about_hero.png"
    />

    <!-- As Unique As You (Intro) -->
    <section class="py-24 bg-white relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2 gap-16 items-center">
          <div class="animate-fade-up">
            <h2 class="text-3xl md:text-4xl font-bold text-[#0B2046] mb-6 leading-tight tracking-tight">
              Asian Traffic Technologies Ltd.
            </h2>
            <p class="text-lg text-slate-600 leading-relaxed mb-6">
              ATT is a multi-dimensional business-oriented company having activities in the sectors of Toll Management & Operation, Ship Building, Navigation & Ship Rescue, Weighing Management, Civil Work & Building Construction, Human & Vehicle Access Control Systems, CCTV Surveillance & Security Systems, and Parking Management.
            </p>
            <p class="text-lg text-slate-600 leading-relaxed mb-8">
              With a multidisciplinary team of engineers, technicians, and project managers, we bring together expertise in electronics, software, civil engineering, and project management to deliver complete solutions that perform reliably in Bangladesh's demanding environment.
            </p>
          </div>
          <div class="relative animate-fade-up delay-200">
            <!-- Decorative abstract shape -->
            <div class="absolute -inset-4 bg-blue-50 border border-blue-100 rounded-[3rem] transform rotate-3"></div>
            <img src="https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&q=80" alt="ATT Office" class="relative rounded-[2.5rem] w-full h-[500px] object-cover shadow-2xl" />
          </div>
        </div>
      </div>
    </section>

    <!-- Smart Counter Section -->
    <section class="relative bg-[#0B2046] py-16 overflow-hidden">
      <!-- Dotted Pattern Overlay -->
      <div class="absolute inset-0 bg-dots pointer-events-none opacity-50"></div>
      
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 md:gap-4 divide-y md:divide-y-0 md:divide-x divide-white/20">
          
          <div v-for="(stat, idx) in companyStats" :key="stat.label" class="flex flex-col items-center justify-center pt-8 md:pt-0">
            <div class="text-4xl md:text-5xl font-black text-white flex items-center mb-1 drop-shadow-sm">
              <AnimatedCounter :value="stat.value" :suffix="stat.suffix" :duration="2000" />
            </div>
            <div class="text-white text-xs md:text-sm font-bold uppercase tracking-widest text-center">{{ stat.label }}</div>
          </div>

        </div>
      </div>
    </section>

    <!-- Vision & Mission -->
    <section id="mission-vision" class="py-24 relative overflow-hidden bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <h2 class="text-3xl md:text-4xl font-bold text-[#0B2046] mb-12 animate-fade-up text-center">Vision & Mission</h2>

        <div class="grid md:grid-cols-2 gap-8">
          <!-- Vision Card -->
          <div class="bg-white rounded-3xl p-10 lg:p-12 shadow-xl border border-slate-200 hover:border-blue-200 transition-colors animate-fade-up delay-100">
            <svg class="w-16 h-16 text-blue-600 mb-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" />
            </svg>
            <h3 class="text-3xl font-black text-slate-900 mb-6">Vision</h3>
            <p class="text-lg text-slate-600 leading-relaxed">
              In a world where complexity increasingly touches every aspect of our daily lives, we will lead in bringing sense and simplicity to people.
            </p>
          </div>

          <!-- Mission Card -->
          <div class="bg-white rounded-3xl p-10 lg:p-12 shadow-xl border border-slate-200 hover:border-blue-200 transition-colors animate-fade-up delay-200">
            <svg class="w-16 h-16 text-blue-600 mb-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z" />
            </svg>
            <h3 class="text-3xl font-black text-slate-900 mb-6">Mission</h3>
            <ul class="space-y-5">
              <li class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-600 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
                <span class="text-slate-600 text-lg leading-relaxed">To hold the leadership in Bangladesh by means of continuous strive in offering quality management for Operation & Maintenance of ETC for Roads & Highways.</span>
              </li>
              <li class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-600 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
                <span class="text-slate-600 text-lg leading-relaxed">To become the market leader for Highways Systems Technology development in Bangladesh.</span>
              </li>
              <li class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-600 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
                <span class="text-slate-600 text-lg leading-relaxed">To provide proper security system all over Bangladesh.</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Sister Concerns Grid -->
    <section class="py-24 bg-white overflow-hidden">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl md:text-4xl font-bold text-[#0B2046] mb-12 text-center animate-fade-up">Sister Concerns</h2>
        
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div class="bg-slate-50 rounded-3xl border border-slate-200 h-64 flex flex-col items-center justify-center p-6 text-center hover:bg-white hover:border-blue-200 hover:shadow-lg transition-all duration-300 animate-fade-up delay-100 group">
            <div class="w-16 h-16 bg-white rounded-2xl flex items-center justify-center p-2 mb-6 shadow-sm group-hover:scale-110 group-hover:shadow-md transition-all duration-300">
              <img src="/images/logo_mehboob_nav.png" alt="Mehboob & Masood Navigation" class="w-full h-full object-contain" />
            </div>
            <h3 class="font-bold text-slate-900 text-lg mb-2 leading-tight">Mehboob & Masood</h3>
            <p class="text-blue-600 font-bold text-[10px] uppercase tracking-widest">Ship Operation</p>
          </div>
          <div class="bg-slate-50 rounded-3xl border border-slate-200 h-64 flex flex-col items-center justify-center p-6 text-center hover:bg-white hover:border-blue-200 hover:shadow-lg transition-all duration-300 animate-fade-up delay-200 group">
            <div class="w-16 h-16 bg-white rounded-2xl flex items-center justify-center p-2 mb-6 shadow-sm group-hover:scale-110 group-hover:shadow-md transition-all duration-300">
              <img src="/images/logo_shams_nav.png" alt="Shams Navigation" class="w-full h-full object-contain" />
            </div>
            <h3 class="font-bold text-slate-900 text-lg mb-2 leading-tight">Shams Navigation</h3>
            <p class="text-blue-600 font-bold text-[10px] uppercase tracking-widest">Carrier Operation</p>
          </div>
          <div class="bg-slate-50 rounded-3xl border border-slate-200 h-64 flex flex-col items-center justify-center p-6 text-center hover:bg-white hover:border-blue-200 hover:shadow-lg transition-all duration-300 animate-fade-up delay-300 group">
            <div class="w-16 h-16 bg-white rounded-2xl flex items-center justify-center p-2 mb-6 shadow-sm group-hover:scale-110 group-hover:shadow-md transition-all duration-300">
              <img src="/images/logo_mehboob_builders.png" alt="Engr. Mehboob Ship Builders" class="w-full h-full object-contain" />
            </div>
            <h3 class="font-bold text-slate-900 text-lg mb-2 leading-tight">Engr. Mehboob Builders</h3>
            <p class="text-blue-600 font-bold text-[10px] uppercase tracking-widest">Manufacturing</p>
          </div>
          <div class="bg-slate-50 rounded-3xl border border-slate-200 h-64 flex flex-col items-center justify-center p-6 text-center hover:bg-white hover:border-blue-200 hover:shadow-lg transition-all duration-300 animate-fade-up delay-400 group">
            <div class="w-16 h-16 bg-white rounded-2xl flex items-center justify-center p-2 mb-6 shadow-sm group-hover:scale-110 group-hover:shadow-md transition-all duration-300">
              <img src="/images/logo_am_corp.png" alt="A M Corporation" class="w-full h-full object-contain" />
            </div>
            <h3 class="font-bold text-slate-900 text-lg mb-2 leading-tight">A M Corporation</h3>
            <p class="text-blue-600 font-bold text-[10px] uppercase tracking-widest">General Trading</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Board of Directors -->
    <section id="board" class="py-24 bg-slate-50 overflow-hidden">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-20 animate-fade-up">
          <h2 class="text-3xl md:text-4xl font-bold text-[#0B2046] mb-6">Board of Directors</h2>
          <div class="w-24 h-1 bg-blue-600 mx-auto rounded-full"></div>
        </div>
        
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-x-8 gap-y-24 text-center mt-16 pb-8">
          <div v-for="(member, idx) in board" :key="member.name" class="group animate-fade-up h-full" :class="`delay-${(idx + 1) * 100}`">
            
            <!-- Card Container -->
            <div class="bg-white rounded-[2rem] p-6 pt-0 flex flex-col items-center h-full border border-slate-200 hover:border-blue-200 hover:bg-blue-50/50 transition-all duration-500 shadow-lg hover:shadow-xl">
              
              <!-- Protruding Image -->
              <div class="w-48 h-56 -mt-12 mb-6 rounded-2xl relative z-10 group-hover:-translate-y-2 transition-all duration-300 mx-auto shadow-xl">
                <div class="w-full h-full rounded-2xl overflow-hidden bg-white relative">
                  <img :src="`/People_images/${member.image}`" :alt="member.name" class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500" />
                  
                  <!-- Standard animated bottom border line -->
                  <div class="absolute bottom-0 left-0 h-[6px] bg-blue-600 w-0 group-hover:w-full transition-all duration-500 ease-out z-20"></div>
                </div>
              </div>
              
              <!-- Content -->
              <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-blue-600 transition-colors">{{ member.name }}</h3>
              <div class="text-blue-600 font-bold uppercase tracking-widest text-xs mb-4">{{ member.title }}</div>
              <p class="text-slate-600 text-sm leading-relaxed mb-6 flex-grow">{{ member.bio }}</p>
              
              <!-- Social Links -->
              <div class="flex gap-3 justify-center mt-auto pb-2">
                <a href="#" class="w-9 h-9 rounded-full bg-slate-50 flex items-center justify-center text-slate-500 hover:bg-blue-600 hover:text-white transition-all duration-300 border border-slate-200">
                  <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                </a>
                <a href="#" class="w-9 h-9 rounded-full bg-slate-50 flex items-center justify-center text-slate-500 hover:bg-blue-800 hover:text-white transition-all duration-300 border border-slate-200">
                  <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                </a>
                <a href="#" class="w-9 h-9 rounded-full bg-slate-50 flex items-center justify-center text-slate-500 hover:bg-blue-600 hover:text-white transition-all duration-300 border border-slate-200">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path></svg>
                </a>
              </div>
            </div>
            
          </div>
        </div>
      </div>
    </section>

  </main>
</template>

<style scoped>
.bg-dots {
  background-image: radial-gradient(rgba(255, 255, 255, 0.25) 2px, transparent 2px);
  background-size: 24px 24px;
}
</style>

<script setup lang="ts">
import AnimatedCounter from '~/components/common/AnimatedCounter.vue'
import PageHero from '~/components/common/PageHero.vue'

useSeoMeta({
  title: 'About ATT — Asian Traffic Technologies Ltd',
  description: 'Learn about Asian Traffic Technologies Ltd — our mission, vision, board of directors, and 25+ years of delivering ITS solutions in Bangladesh.',
})



const companyStats = [
  { value: 2002, label: 'Year Established', sub: 'Inception of ATT', suffix: '' },
  { value: 80, label: 'Market Share', sub: 'In Core Businesses', suffix: '%' },
  { value: 500, label: 'Workforce', sub: 'Technical & Commercial', suffix: '+' },
  { value: 31, label: 'Owned Vessels', sub: 'Cargo & Tankers', suffix: '' },
]

const board = [
  {
    name: 'Engr. Mehboob Kabir',
    image: 'mehboob_kabir.PNG',
    title: 'Managing Director',
    bio: 'B.Sc in CSE, DBA from Mehran Engineering University. Guided ATT\'s business strategies and rapid growth since 1998.',
  },
  {
    name: 'Dr. Sifat Farhana Nahid',
    image: 'sifat_farhana.PNG',
    title: 'Deputy Managing Director',
    bio: 'M.B.B.S in Dhaka National Medical College. Key person in PR and Finance, ensuring operational health.',
  },
  {
    name: 'Shams Kader',
    image: 'shams_kader.PNG',
    title: 'Director',
    bio: 'Maintaining on-site operations of the construction sector with dedication, technical knowledge, and a focus on safety.',
  },
  {
    name: 'Nafisa Nahar',
    image: 'nafisa_nahar.PNG',
    title: 'Director',
    bio: 'Overseeing maritime operations with efficiency, precision, and strong leadership.',
  },
]
</script>
