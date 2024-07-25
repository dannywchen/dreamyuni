<template>
  <header class="py-4 px-8 flex justify-between items-center bg-gray-900 text-white">
    <div class="flex items-center space-x-4">
      <img src="https://placehold.co/40x40" alt="Easy UI Logo" class="h-8 w-8">
      <span class="text-xl font-bold">Easy UI <span class="text-xs bg-gray-700 px-2 py-1 rounded">Beta</span></span>
    </div>
    <nav class="hidden md:flex space-x-6">
      <a href="#" class="hover:text-gray-300">Templates</a>
      <a href="#" class="hover:text-gray-300">GitHub <i class="fas fa-external-link-alt text-xs"></i></a>
      <a href="#" class="hover:text-gray-300">Easy MVP <i class="fas fa-external-link-alt text-xs"></i></a>
    </nav>
    <div class="flex items-center space-x-4">
      <button class="bg-white text-black px-4 py-2 rounded-full hover:bg-gray-200">Get Easy MVP</button>
      <button @click="toggleDarkMode" class="text-xl">
        <i :class="isDarkMode ? 'fas fa-sun' : 'fas fa-moon'"></i>
      </button>
    </div>
  </header>

  <slot></slot>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import { gsap } from 'gsap';

const isDarkMode = ref(true);

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle('dark');
};

onMounted(() => {
  gsap.from("header", { duration: 1, y: -50, opacity: 0, ease: "power3.out" });
  document.documentElement.classList.add('dark');
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

header {
  font-family: 'Inter', sans-serif;
}

:root {
  --bg-color: #ffffff;
  --text-color: #000000;
}

:root.dark {
  --bg-color: #1a202c;
  --text-color: #ffffff;
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
}
</style>
