<template>
  <div class="bg-white">
    <!-- ===== HERO ===== -->
    <section class="bg-dark min-h-[630px] flex flex-col justify-center relative overflow-hidden">
      <div
        class="max-w-[1280px] mx-auto w-full px-12 flex items-center justify-between gap-8 py-20"
      >
        <!-- Left: text -->
        <div class="flex flex-col gap-8 max-w-[540px]">
          <div class="flex flex-col gap-2">
            <h1 class="font-raleway font-extrabold text-[44px] leading-tight text-white">
              Peter Kysel
            </h1>
            <p class="font-mono text-sm text-muted leading-6 tracking-[0.14px] max-w-[492px]">
              Intro text: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
              tempor incididunt ut labore et dolore magna aliqua.
            </p>
          </div>
          <a
            href="#contact"
            class="inline-flex items-center gap-3 bg-brand border border-brand-border px-16 py-5 rounded font-mono font-bold text-white text-base shadow-[0px_8px_30px_0px_rgba(63,142,0,0.5)] transition-opacity hover:opacity-90 self-start"
          >
            Let's get started
            <svg width="6" height="10" viewBox="0 0 6 10" fill="none">
              <path
                d="M1 1l4 4-4 4"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </a>
        </div>

        <!-- Right: photo placeholder -->
        <div
          class="shrink-0 w-[350px] h-[350px] rounded-full bg-[#2a2a2a] flex items-center justify-center text-muted font-mono text-sm"
        >
          Photo
        </div>
      </div>

      <!-- Worked with -->
      <div class="max-w-[1280px] mx-auto w-full px-12 pb-12">
        <p class="font-mono text-sm text-white mb-4">Worked with</p>
        <div class="flex gap-5 flex-wrap">
          <div
            v-for="logo in clientLogos"
            :key="logo"
            class="border border-[#333] rounded-md w-[160px] h-[60px] flex items-center justify-center"
          >
            <span class="font-mono text-xs text-muted">{{ logo }}</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== CASE STUDIES ===== -->
    <section class="py-20 bg-white">
      <div class="max-w-[1280px] mx-auto px-12">
        <!-- Heading -->
        <div class="text-center mb-16">
          <h2 class="font-raleway font-extrabold text-[34px] text-[#080808]">Case Studies</h2>
          <p
            class="font-mono text-sm text-muted mt-4 max-w-[570px] mx-auto leading-6 tracking-[0.14px]"
          >
            Solving user &amp; business problems since last 15+ years.<br />
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna aliqua.
          </p>
        </div>

        <!-- Cases -->
        <div class="flex flex-col gap-16">
          <div
            v-for="(cs, i) in caseStudies"
            :key="cs.title + i"
            class="flex items-center gap-12"
            :class="i % 2 === 1 ? 'flex-row-reverse' : ''"
          >
            <!-- Image placeholder -->
            <div
              class="shrink-0 w-[445px] h-[300px] rounded-lg bg-gray-200 flex items-center justify-center text-gray-400 font-mono text-sm"
            >
              Image
            </div>

            <!-- Text -->
            <div class="flex flex-col gap-4">
              <span
                class="inline-block self-start px-3 rounded-full font-mono font-bold text-xs leading-6 tracking-[0.12px]"
                :style="{ backgroundColor: cs.tagBg, color: cs.tagColor }"
              >
                {{ cs.tag }}
              </span>
              <h3 class="font-raleway font-extrabold text-2xl text-[#080808]">{{ cs.title }}</h3>
              <p class="font-mono text-sm text-muted leading-6 tracking-[0.14px] max-w-[421px]">
                {{ cs.description }}
              </p>
              <a
                :href="cs.href"
                class="inline-flex items-center gap-3 self-start px-6 py-2.5 rounded font-mono font-bold text-sm text-white transition-opacity hover:opacity-90"
                :style="{
                  backgroundColor: cs.btnColor,
                  boxShadow: `0px 8px 30px 0px ${cs.btnColor}33`,
                }"
              >
                View case study
                <svg width="6" height="10" viewBox="0 0 6 10" fill="none">
                  <path
                    d="M1 1l4 4-4 4"
                    stroke="currentColor"
                    stroke-width="1.5"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== TESTIMONIALS ===== -->
    <section class="bg-dark py-20">
      <div class="max-w-[1280px] mx-auto px-12">
        <!-- Heading -->
        <div class="text-center mb-16">
          <h2 class="font-raleway font-extrabold text-[34px] text-white">Testimonials</h2>
          <p
            class="font-mono text-sm text-muted mt-4 max-w-[570px] mx-auto leading-6 tracking-[0.14px]"
          >
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna aliqua.
          </p>
        </div>

        <!-- 2x2 grid -->
        <div class="grid grid-cols-2 gap-6">
          <div
            v-for="t in testimonials"
            :key="t.name + t.quote.slice(0, 20)"
            class="border border-card-border rounded-lg p-8 flex flex-col justify-between gap-8"
          >
            <p class="font-mono text-sm text-muted leading-6 tracking-[0.14px]">{{ t.quote }}</p>
            <div class="flex items-center gap-4">
              <div class="w-[50px] h-[50px] rounded-full bg-[#2a2a2a] shrink-0" />
              <span class="font-raleway font-bold text-lg text-white">{{ t.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== RECENT WORK ===== -->
    <section class="py-20 bg-white">
      <div class="max-w-[1280px] mx-auto px-12">
        <!-- Heading -->
        <div class="text-center mb-16">
          <h2 class="font-raleway font-extrabold text-[34px] text-[#080808]">Recent Work</h2>
          <p
            class="font-mono text-sm text-muted mt-4 max-w-[570px] mx-auto leading-6 tracking-[0.14px]"
          >
            Solving user &amp; business problems since last 15+ years.<br />
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna aliqua.
          </p>
        </div>

        <!-- Cards + nav -->
        <div class="flex items-center gap-4">
          <button
            class="shrink-0 w-8 h-8 rounded-full border border-gray-300 flex items-center justify-center text-gray-500 hover:bg-gray-100 transition-colors disabled:opacity-30"
            :disabled="workPage === 0"
            aria-label="Previous"
            @click="workPage--"
          >
            <svg width="8" height="14" viewBox="0 0 8 14" fill="none">
              <path
                d="M7 1L1 7l6 6"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </button>

          <div class="flex gap-8 flex-1">
            <div v-for="work in visibleWork" :key="work.title" class="flex-1 flex flex-col gap-4">
              <div
                class="w-full h-[300px] rounded-lg bg-gray-200 flex items-center justify-center text-gray-400 font-mono text-sm"
              >
                Image
              </div>
              <h3 class="font-raleway font-extrabold text-2xl text-[#080808]">{{ work.title }}</h3>
              <p class="font-mono text-sm text-muted leading-6 tracking-[0.14px]">
                {{ work.description }}
              </p>
              <a
                :href="work.href"
                class="inline-flex items-center gap-3 self-start bg-brand border border-brand-border px-6 py-2.5 rounded font-mono font-bold text-sm text-white shadow-[0px_8px_30px_0px_rgba(63,142,0,0.3)] transition-opacity hover:opacity-90"
              >
                Know more
                <svg width="6" height="10" viewBox="0 0 6 10" fill="none">
                  <path
                    d="M1 1l4 4-4 4"
                    stroke="currentColor"
                    stroke-width="1.5"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </a>
            </div>
          </div>

          <button
            class="shrink-0 w-8 h-8 rounded-full border border-gray-300 flex items-center justify-center text-gray-500 hover:bg-gray-100 transition-colors disabled:opacity-30"
            :disabled="workPage >= maxWorkPage"
            aria-label="Next"
            @click="workPage++"
          >
            <svg width="8" height="14" viewBox="0 0 8 14" fill="none">
              <path
                d="M1 1l6 6-6 6"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </button>
        </div>
      </div>
    </section>

    <!-- ===== GET IN TOUCH ===== -->
    <section id="contact" class="bg-dark py-20">
      <div class="max-w-[1280px] mx-auto px-12">
        <!-- Heading -->
        <div class="text-center mb-16">
          <h2 class="font-raleway font-extrabold text-[34px] text-white">Get In Touch</h2>
          <p
            class="font-mono text-sm text-muted mt-4 max-w-[570px] mx-auto leading-6 tracking-[0.14px]"
          >
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna aliqua.
          </p>
        </div>

        <!-- Form -->
        <form class="flex flex-col gap-5 max-w-[350px] mx-auto" @submit.prevent="submitForm">
          <div class="flex flex-col gap-1.5">
            <label class="font-mono font-semibold text-xs text-white">Email</label>
            <input
              v-model="form.email"
              type="email"
              placeholder="Please enter your email"
              class="bg-[#f8f8f8] border border-[#d8d8d8] rounded px-3 h-10 font-mono text-xs text-[#757575] outline-none focus:border-brand transition-colors"
              required
            />
          </div>
          <div class="flex flex-col gap-1.5">
            <label class="font-mono font-semibold text-xs text-white">Mobile</label>
            <input
              v-model="form.mobile"
              type="tel"
              placeholder="Enter mobile"
              class="bg-[#f8f8f8] border border-[#d8d8d8] rounded px-3 h-10 font-mono text-xs text-[#757575] outline-none focus:border-brand transition-colors"
            />
          </div>
          <div class="flex flex-col gap-1.5">
            <label class="font-mono font-semibold text-xs text-white">Message</label>
            <textarea
              v-model="form.message"
              placeholder="Enter your message"
              rows="5"
              class="bg-[#f8f8f8] border border-[#d8d8d8] rounded px-3 py-2 font-mono text-xs text-[#757575] outline-none focus:border-brand transition-colors resize-none"
              required
            />
          </div>
          <button
            type="submit"
            class="inline-flex items-center justify-center gap-3 bg-brand border border-brand-border px-6 py-4 rounded font-mono font-bold text-sm text-white shadow-[0px_8px_30px_0px_rgba(63,142,0,0.3)] transition-opacity hover:opacity-90"
          >
            Submit
            <svg width="6" height="10" viewBox="0 0 6 10" fill="none">
              <path
                d="M1 1l4 4-4 4"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </button>
        </form>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'

const clientLogos = ['ClickUp', 'Dropbox', 'Paychex', 'Elastic', 'Stripe']

const caseStudies = [
  {
    tag: 'Fintech',
    tagBg: '#fff6e9',
    tagColor: '#ffa217',
    btnColor: '#ffa217',
    title: 'Work name here',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. sed do eiusmod tempor incididunt ut labore et dolore magna.',
    href: '#',
  },
  {
    tag: 'EdTech',
    tagBg: '#d0e6ff',
    tagColor: '#000aff',
    btnColor: '#000aff',
    title: 'Work name here',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. sed do eiusmod tempor incididunt ut labore et dolore magna.',
    href: '#',
  },
  {
    tag: 'Pharma',
    tagBg: '#e0fff8',
    tagColor: '#2ab090',
    btnColor: '#2ab090',
    title: 'Work name here',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. sed do eiusmod tempor incididunt ut labore et dolore magna.',
    href: '#',
  },
]

const testimonials = [
  {
    name: 'Client Name',
    quote:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
  },
  {
    name: 'Client Name',
    quote:
      'Consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
  },
  {
    name: 'Client Name',
    quote:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
  },
  {
    name: 'Client Name',
    quote:
      'Consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
  },
]

const recentWork = [
  {
    title: 'Work name here',
    description:
      'Labore et dolore magna aliqua. sed do eiusmod tempor incididunt ut labore et dolore magna.',
    href: '#',
  },
  {
    title: 'Work name here',
    description:
      'Rempor incididunt ut labore et dolore magna aliqua. sed do eiusmod tempor incididunt u',
    href: '#',
  },
  {
    title: 'Work name here',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor.',
    href: '#',
  },
]

const CARDS_PER_PAGE = 2
const workPage = ref(0)
const maxWorkPage = computed(() => Math.ceil(recentWork.length / CARDS_PER_PAGE) - 1)
const visibleWork = computed(() =>
  recentWork.slice(
    workPage.value * CARDS_PER_PAGE,
    workPage.value * CARDS_PER_PAGE + CARDS_PER_PAGE,
  ),
)

const form = ref({ email: '', mobile: '', message: '' })

function submitForm() {
  alert('Message sent!')
  form.value = { email: '', mobile: '', message: '' }
}
</script>
