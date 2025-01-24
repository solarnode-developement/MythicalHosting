<template>
  <div class="min-h-screen bg-[#0a0a0f] text-white overflow-hidden">
    <AnimatedBackground />
    <div id="glowing-cursor"></div>
    <Navbar />
    <Hero />
    <Partners />
    <HostingPlans />
    <GamePlans />
    <Features />
    <DataCenter />
    <Reviews />
    <Faq />
    <Footer />
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
import Navbar from '@/components/Navbar.vue'
import Hero from '@/components/Hero.vue'
import Partners from '@/components/Partners.vue'
import HostingPlans from '@/components/HostingPlans.vue'
import GamePlans from '@/components/GamePlans.vue'
import Features from '@/components/Features.vue'
import DataCenter from '@/components/DataCenter.vue'
import Reviews from '@/components/Reviews.vue'
import Faq from '@/components/Faq.vue'
import Footer from '@/components/Footer.vue'
import AnimatedBackground from '@/components/AnimatedBackground.vue'

onMounted(() => {
  document.documentElement.classList.add('dark')

  const cursor = document.getElementById('glowing-cursor')
  document.addEventListener('mousemove', (e) => {
    if (cursor) {
      cursor.style.left = e.clientX + 'px'
      cursor.style.top = e.clientY + 'px'
    }
  })
})
</script>

