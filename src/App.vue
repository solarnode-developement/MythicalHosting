<script setup lang="ts">
import { RouterView } from 'vue-router'
import { ref, onMounted } from 'vue';
const isLoading = ref(true)

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false
  }, 100)
})
</script>

<template>
  <div v-if="isLoading" class="preloader">
    <div class="loading">
      <div class="dot"></div>
      <div class="dot"></div>
      <div class="dot"></div>
      <div class="dot"></div>
      <div class="dot"></div>
    </div>
  </div>
  <div v-else>
    <RouterView />
  </div>
</template>

<style scoped>
.preloader {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #000000;
}

.loading {
  display: flex;
  gap: 8px;
}

.dot {
  width: 20px;
  height: 20px;
  background: #ffffff;
  border-radius: 50%;
  animation: bounce 0.5s cubic-bezier(0.19, 0.57, 0.3, 0.98) infinite;
}

.dot:nth-child(2) {
  animation-delay: 0.1s;
}

.dot:nth-child(3) {
  animation-delay: 0.2s;
}

.dot:nth-child(4) {
  animation-delay: 0.3s;
}

.dot:nth-child(5) {
  animation-delay: 0.4s;
}

@keyframes bounce {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-20px);
  }
}
</style>
<style>
:root {
  --purple-glow: 0 0 80px rgba(147, 51, 234, 0.2);
}

.glass-effect {
  background-color: rgba(31, 41, 55, 0.1);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(107, 114, 128, 0.5);
}

@keyframes float {

  0%,
  100% {
    transform: translateY(0px);
  }

  50% {
    transform: translateY(-20px);
  }
}

@keyframes pulse {

  0%,
  100% {
    opacity: 1;
  }

  50% {
    opacity: 0.5;
  }
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-pulse-slow {
  animation: pulse 4s ease-in-out infinite;
}

.animate-rotate {
  animation: rotate 20s linear infinite;
}

#glowing-cursor {
  width: 20px;
  height: 20px;
  background: radial-gradient(circle, rgba(147, 51, 234, 0.8) 0%, rgba(147, 51, 234, 0.4) 50%, transparent 70%);
  border-radius: 50%;
  position: fixed;
  pointer-events: none;
  z-index: 9999;
  transition: 0.1s ease;
}

/* Custom Scrollbar */
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #1a1a2e;
}

::-webkit-scrollbar-thumb {
  background: #4c1d95;
  border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
  background: #6d28d9;
}

/* Mobile Responsiveness */
@media (max-width: 768px) {
  .container {
    padding-left: 1rem;
    padding-right: 1rem;
  }

  h1 {
    font-size: 2.5rem !important;
  }

  h2 {
    font-size: 2rem !important;
  }

  .grid {
    grid-template-columns: 1fr !important;
  }
}
</style>
