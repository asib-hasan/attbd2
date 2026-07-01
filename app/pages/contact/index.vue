<template>
  <main class="bg-slate-50 min-h-screen">
    <PageHero
      title="Contact Us"
      subtitle="Get in touch with our team for project consultations, product enquiries, or technical support. We'd love to hear from you."
      label="Get In Touch"
      bgImage="/slider/new_toll_plaza.png"
    />

    <section class="py-24 bg-slate-50 border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">

          <!-- Contact Info Cards -->
          <div class="space-y-6">
            <div v-for="info in contactInfo" :key="info.label" :class="['bg-white border border-slate-200 border-l-[4px] p-8 rounded-3xl shadow-lg hover:shadow-2xl hover:-translate-y-1 transition-all duration-300 relative overflow-hidden group', info.color]">
              <!-- Decorative background element for info cards -->
              <div class="absolute -right-12 -top-12 w-32 h-32 bg-slate-50 rounded-full group-hover:scale-150 transition-transform duration-700 pointer-events-none opacity-50 z-0"></div>
              
              <div class="relative z-10">
                <div class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-3">{{ info.label }}</div>
                <div v-for="line in info.lines" :key="line">
                  <a v-if="info.href" :href="`${info.href}${line}`" class="text-slate-900 font-bold hover:text-blue-600 transition-colors block text-lg mb-1">{{ line }}</a>
                  <p v-else class="text-slate-600 font-medium text-base leading-relaxed">{{ line }}</p>
                </div>
              </div>
            </div>

            <!-- Map placeholder -->
            <div class="bg-slate-50 border border-slate-200 rounded-3xl p-8 text-slate-900 relative overflow-hidden shadow-lg group hover:border-blue-200 transition-all duration-300 mt-8">
              <div class="absolute -bottom-10 -right-10 w-40 h-40 bg-blue-600/10 blur-3xl rounded-full group-hover:bg-blue-600/20 transition-colors duration-500"></div>
              <div class="text-[10px] font-bold text-blue-600 uppercase tracking-widest mb-3 relative z-10">Location</div>
              <p class="text-sm text-slate-600 leading-relaxed mb-6 relative z-10">House #67, Road #27, Gulshan Circle #1, Dhaka-1212, Bangladesh</p>
              <a
                href="https://maps.google.com/?q=Gulshan+Circle+1+Dhaka+Bangladesh"
                target="_blank"
                rel="noopener"
                class="inline-flex items-center gap-2 text-blue-600 text-sm font-bold hover:text-blue-800 transition-colors uppercase tracking-widest relative z-10"
              >
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"/></svg>
                Google Maps
              </a>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="lg:col-span-2">
            <div class="bg-white rounded-[2.5rem] border border-slate-200 shadow-2xl p-8 md:p-14 relative overflow-hidden h-full flex flex-col">
              <!-- Subtle decorative accent -->
              <div class="absolute top-0 right-0 w-80 h-80 bg-gradient-to-br from-blue-50 to-transparent rounded-full blur-3xl -mr-20 -mt-20 pointer-events-none"></div>
              <div class="absolute bottom-0 left-0 w-64 h-64 bg-gradient-to-tr from-slate-50 to-transparent rounded-full blur-3xl -ml-20 -mb-20 pointer-events-none"></div>
              
              <div class="mb-12 border-l-[4px] border-blue-600 pl-6 relative z-10">
                <div class="text-[10px] font-bold text-blue-600 uppercase tracking-widest mb-2">Send us a Message</div>
                <h2 class="text-3xl md:text-5xl font-black text-slate-900 mb-4 tracking-tight leading-tight">How can we help you?</h2>
                <p class="text-slate-500 text-base leading-relaxed max-w-xl">Fill in the form below and our team will get back to you within 1 business day.</p>
              </div>

              <form @submit.prevent="submitForm" class="space-y-6">
                <div class="grid sm:grid-cols-2 gap-6">
                  <div>
                    <label class="form-label" for="name">Full Name *</label>
                    <input id="name" v-model="form.name" type="text" class="form-input" placeholder="Your full name" required />
                  </div>
                  <div>
                    <label class="form-label" for="email">Email Address *</label>
                    <input id="email" v-model="form.email" type="email" class="form-input" placeholder="your@email.com" required />
                  </div>
                </div>

                <div class="grid sm:grid-cols-2 gap-6">
                  <div>
                    <label class="form-label" for="phone">Phone Number</label>
                    <input id="phone" v-model="form.phone" type="tel" class="form-input" placeholder="+88 01XXX XXX XXX" />
                  </div>
                  <div>
                    <label class="form-label" for="subject">Subject *</label>
                    <input id="subject" v-model="form.subject" type="text" class="form-input" placeholder="What is this regarding?" required />
                  </div>
                </div>

                <div>
                  <label class="form-label" for="company">Organization / Company</label>
                  <input id="company" v-model="form.company" type="text" class="form-input" placeholder="Your organization name" />
                </div>

                <div>
                  <label class="form-label" for="message">Message *</label>
                  <textarea id="message" v-model="form.message" class="form-input min-h-[160px] resize-none" placeholder="Please describe your requirements in detail..." required></textarea>
                </div>

                <!-- Success message -->
                <Transition name="dropdown">
                  <div v-if="submitted" class="flex items-center gap-3 p-5 bg-green-500/10 border border-green-500/20 rounded-2xl text-green-400 text-sm font-bold">
                    <svg class="w-5 h-5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    Thank you! Your message has been sent. We'll be in touch shortly.
                  </div>
                </Transition>

                <div class="pt-4 relative z-10">
                  <button
                    type="submit"
                    :disabled="submitting"
                    class="w-full sm:w-auto px-10 py-4 bg-blue-600 hover:bg-blue-700 text-white disabled:opacity-60 font-bold uppercase tracking-widest rounded-full transition-all duration-300 flex items-center justify-center gap-3 group shadow-lg hover:shadow-xl hover:-translate-y-0.5"
                  >
                    <svg v-if="submitting" class="w-5 h-5 animate-spin" fill="none" viewBox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"/><path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"/></svg>
                    {{ submitting ? 'Sending...' : 'Send Message' }}
                    <svg v-if="!submitting" class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Contact Us — ATT | Asian Traffic Technologies Ltd',
  description: 'Contact Asian Traffic Technologies Ltd for ITS solutions, product inquiries, project consultations, and technical support. Based in Dhaka, Bangladesh.',
})

const form = reactive({
  name: '',
  email: '',
  phone: '',
  company: '',
  subject: '',
  message: '',
})

const submitting = ref(false)
const submitted = ref(false)

async function submitForm() {
  submitting.value = true
  // Simulate API call
  await new Promise(r => setTimeout(r, 1200))
  submitting.value = false
  submitted.value = true
  // Reset form
  Object.assign(form, { name: '', email: '', phone: '', company: '', subject: '', message: '' })
  setTimeout(() => { submitted.value = false }, 6000)
}

const contactInfo = [
  {
    label: 'Phone',
    color: 'border-l-blue-500',
    href: 'tel:',
    lines: ['+88-2-8832313', '+88-2-8832240'],
  },
  {
    label: 'Email',
    color: 'border-l-accent-500',
    href: 'mailto:',
    lines: ['info@att-bd.com'],
  },
  {
    label: 'Office Address',
    color: 'border-l-slate-500',
    href: null,
    lines: ['House #67, Road #27,', 'Gulshan Circle #1,', 'Dhaka-1212, Bangladesh'],
  },
]
</script>

<style scoped>
.form-label {
  display: block;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: #64748b; /* slate-500 */
  margin-bottom: 0.5rem;
}

.form-input {
  width: 100%;
  padding: 1.125rem 1.5rem;
  border: 1px solid #e2e8f0; /* slate-200 */
  border-radius: 1rem;
  font-size: 0.95rem;
  color: #0f172a; /* slate-900 */
  background: #f8fafc; /* slate-50 */
  outline: none;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.form-input:focus {
  border-color: #3b82f6; /* blue-500 */
  background: #ffffff;
  box-shadow: 0 4px 14px 0 rgba(59, 130, 246, 0.15), 0 0 0 4px rgba(59, 130, 246, 0.1);
  transform: translateY(-1px);
}

.form-input::placeholder {
  color: #94a3b8; /* slate-400 */
}
</style>
