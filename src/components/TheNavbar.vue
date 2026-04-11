<template>
  <nav
    class="fixed top-0 left-0 right-0 z-50 grid grid-cols-3 items-center px-12 h-[70px] bg-[#1b1b1b]"
  >
    <!-- Hamburger (mobile only) -->
    <button
      class="md:hidden flex flex-col justify-center gap-[5px] w-8 h-8"
      aria-label="Open menu"
      @click="isOpen = true"
    >
      <span class="block h-[2px] w-6 bg-white rounded" />
      <span class="block h-[2px] w-6 bg-white rounded" />
      <span class="block h-[2px] w-6 bg-white rounded" />
    </button>

    <!-- Desktop nav links (hidden on mobile) -->
    <div class="hidden md:flex justify-center gap-[70px]">
      <RouterLink
        to="/about"
        class="font-mono text-sm tracking-[0.14px] text-muted transition-colors hover:text-white"
        active-class="text-white"
      >
        About
      </RouterLink>
      <RouterLink
        to="/contact"
        class="font-mono text-sm tracking-[0.14px] text-muted transition-colors hover:text-white"
        active-class="text-white"
      >
        Contact
      </RouterLink>
    </div>

    <!-- Spacer (desktop) / empty (mobile) -->
    <div class="hidden md:block" />

    <!-- Social icons -->
    <div class="flex items-center justify-end gap-4">
      <a
        href="https://linkedin.com"
        target="_blank"
        rel="noopener noreferrer"
        class="text-muted hover:text-white transition-colors"
        aria-label="LinkedIn"
      >
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
          <path
            d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
          />
        </svg>
      </a>
      <a
        href="https://behance.net"
        target="_blank"
        rel="noopener noreferrer"
        class="text-muted hover:text-white transition-colors"
        aria-label="Behance"
      >
        <svg width="20" height="14" viewBox="0 0 24 16" fill="currentColor">
          <path
            d="M7.443 0c.826 0 1.584.072 2.272.219a5.2 5.2 0 0 1 1.77.695c.496.317.882.733 1.157 1.247.274.514.411 1.137.411 1.869 0 .802-.181 1.476-.543 2.021-.362.546-.9.997-1.613 1.353.974.28 1.7.782 2.177 1.505.477.724.716 1.6.716 2.627 0 .802-.152 1.5-.455 2.092a4.315 4.315 0 0 1-1.243 1.5 5.638 5.638 0 0 1-1.833.907C9.274 15.945 8.578 16 7.824 16H0V0h7.443zm-.41 6.325c.633 0 1.15-.154 1.55-.461.4-.308.6-.779.6-1.413 0-.356-.065-.652-.194-.888a1.546 1.546 0 0 0-.527-.572 2.244 2.244 0 0 0-.76-.306 4.26 4.26 0 0 0-.913-.093H2.758v3.733h4.275zm.24 6.608c.34 0 .663-.033.968-.1a2.39 2.39 0 0 0 .822-.333c.237-.158.427-.37.568-.638.14-.267.21-.604.21-1.009 0-.8-.224-1.376-.672-1.728-.448-.352-1.044-.528-1.787-.528H2.758v4.336h4.515zM18.994 13.3c.464.452 1.132.678 2.004.678.624 0 1.163-.156 1.616-.469.453-.313.73-.642.83-.988H24c-.35 1.1-.89 1.887-1.617 2.362C21.656 15.358 20.75 16 19.676 16c-.746 0-1.416-.12-2.01-.358a4.294 4.294 0 0 1-1.522-1.01 4.56 4.56 0 0 1-.966-1.569A5.636 5.636 0 0 1 14.84 11c0-.712.114-1.373.34-1.984a4.7 4.7 0 0 1 .969-1.587 4.44 4.44 0 0 1 1.516-1.047 4.886 4.886 0 0 1 1.967-.383c.8 0 1.5.154 2.1.462a4.16 4.16 0 0 1 1.476 1.24c.39.52.67 1.113.837 1.779.168.666.228 1.37.18 2.11h-7.14c.04.95.305 1.657.91 2.71zM21.18 7.98c-.38-.418-.972-.627-1.777-.627-.502 0-.921.083-1.258.25a2.598 2.598 0 0 0-.82.634 2.5 2.5 0 0 0-.452.832 3.756 3.756 0 0 0-.165.878h5.395c-.1-.868-.543-1.549-.923-1.967zM15.375 2.118h6.107v1.5h-6.107z"
          />
        </svg>
      </a>
      <a
        href="https://twitter.com"
        target="_blank"
        rel="noopener noreferrer"
        class="text-muted hover:text-white transition-colors"
        aria-label="Twitter"
      >
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
          <path
            d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.742l7.732-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"
          />
        </svg>
      </a>
    </div>
  </nav>

  <!-- Mobile full-screen overlay -->
  <Teleport to="body">
    <div
      v-if="isOpen"
      class="fixed inset-0 z-[100] bg-[#1b1b1b] flex flex-col items-center pt-32 gap-10"
    >
      <!-- Close button -->
      <button
        class="absolute top-5 left-12 text-muted hover:text-white transition-colors"
        aria-label="Close menu"
        @click="isOpen = false"
      >
        <svg
          width="20"
          height="20"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
        >
          <path d="M18 6L6 18M6 6l12 12" />
        </svg>
      </button>

      <RouterLink
        to="/about"
        class="font-raleway font-extrabold text-3xl text-muted hover:text-white transition-colors"
        active-class="text-white"
        @click="isOpen = false"
      >
        About
      </RouterLink>
      <RouterLink
        to="/contact"
        class="font-raleway font-extrabold text-3xl text-muted hover:text-white transition-colors"
        active-class="text-white"
        @click="isOpen = false"
      >
        Contact
      </RouterLink>
    </div>
  </Teleport>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isOpen = ref(false)
</script>
