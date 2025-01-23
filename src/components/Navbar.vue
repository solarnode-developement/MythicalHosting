<template>
  <nav class="fixed top-0 left-0 w-full backdrop-blur-lg z-50">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex items-center space-x-2">
            <ServerIcon class="w-8 h-8 text-purple-500" />
            <span class="text-2xl font-bold bg-gradient-to-r from-purple-400 to-violet-400 bg-clip-text text-transparent">AuroraVM</span>
          </a>
        </div>
        <div class="hidden md:block">
          <div class="flex items-center space-x-4">
            <a v-for="item in navItems" :key="item" href="#" class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-colors duration-300">
              {{ item }}
            </a>
          </div>
        </div>
        <div class="hidden md:block">
          <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded-md text-sm font-medium transition-colors duration-300">
            Client Area
          </button>
        </div>
        <div class="md:hidden">
          <button @click="toggleMobileMenu" class="text-gray-300 hover:text-white focus:outline-none">
            <MenuIcon v-if="!mobileMenuOpen" class="h-6 w-6" />
            <XIcon v-else class="h-6 w-6" />
          </button>
        </div>
      </div>
    </div>
    <div v-if="mobileMenuOpen" class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a v-for="item in navItems" :key="item" href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium transition-colors duration-300">
          {{ item }}
        </a>
      </div>
      <div class="px-4 py-3">
        <button class="w-full bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded-md text-sm font-medium transition-colors duration-300">
          Get Started
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { ServerIcon, MenuIcon, XIcon } from 'lucide-vue-next'

const navItems = ['Home', 'Services', 'Pricing', 'About', 'Contact']
const mobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

