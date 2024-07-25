<template>
  <div class="min-h-screen bg-black text-white">
    <!-- Header Section -->
    <Navbar />

    <!-- Main Banner Section -->
    <main class="text-center py-20 px-4">
      <div class="inline-block bg-gray-800 text-sm px-3 py-1 rounded-full mb-4">Welcome to DreamyUni</div>
      <h1 class="text-4xl md:text-6xl font-bold mb-6">Dream for Your Uni</h1>
      <p class="text-xl mb-8 max-w-3xl mx-auto">Discover a world of knowledge with DreamyUni. Our platform offers a wide range of courses designed to help you achieve your dreams and excel in your academic journey.</p>
      <div class="flex justify-center space-x-4 mb-8">
        <button class="bg-white text-black px-6 py-3 rounded-full hover:bg-gray-200">Explore Courses</button>
        <button class="bg-blue-600 text-white px-6 py-3 rounded-full hover:bg-blue-700">Join DreamyUni</button>
      </div>
      <div class="flex justify-center items-center">
        <div class="flex -space-x-2">
          <img v-for="i in 5" :key="i" :src="'https://placehold.co/40x40'" :alt="`User ${i}`" class="w-8 h-8 rounded-full border-2 border-black">
        </div>
        <span class="ml-2">+99 students</span>
      </div>
    </main>

    <!-- Testimonials Section -->
    <section class="py-20 px-4">
      <h2 class="text-3xl font-bold text-center mb-2">What Our Students Say</h2>
      <p class="text-center mb-12">Hear from those who have experienced the DreamyUni difference.</p>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <div v-for="i in 6" :key="i" class="bg-gray-800 p-6 rounded-lg">
          <div class="flex items-center mb-4">
            <img :src="'https://placehold.co/40x40'" :alt="`Testimonial ${i}`" class="w-10 h-10 rounded-full mr-4">
            <div>
              <h3 class="font-bold">Student {{ i }}</h3>
              <p class="text-sm text-gray-400">@student{{ i }}</p>
            </div>
          </div>
          <p>"DreamyUni has transformed my learning experience. The courses are top-notch and the community is incredibly supportive. 🌟"</p>
        </div>
      </div>
    </section>

    <!-- Footer Section -->
    <footer class="bg-gray-900 py-12 px-4">
      <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-8">
        <div>
          <h4 class="font-bold mb-4">DreamyUni</h4>
          <p class="text-sm text-gray-400">Empowering students to achieve their dreams, one course at a time.</p>
        </div>
        <div>
          <h4 class="font-bold mb-4">Product</h4>
          <ul class="space-y-2">
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">Courses</a></li>
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">Pricing</a></li>
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">Documentation</a></li>
          </ul>
        </div>
        <div>
          <h4 class="font-bold mb-4">Company</h4>
          <ul class="space-y-2">
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">About Us</a></li>
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">Blog</a></li>
            <li><a href="#" class="text-sm text-gray-400 hover:text-white">Careers</a></li>
          </ul>
        </div>
        <div>
          <h4 class="font-bold mb-4">Connect</h4>
          <div class="flex space-x-4">
            <a href="#" class="text-gray-400 hover:text-white"><i class="fab fa-twitter"></i></a>
            <a href="#" class="text-gray-400 hover:text-white"><i class="fab fa-github"></i></a>
            <a href="#" class="text-gray-400 hover:text-white"><i class="fab fa-linkedin"></i></a>
          </div>
        </div>
      </div>
      <div class="mt-8 text-center text-sm text-gray-400">
        &copy; 2023 DreamyUni. All rights reserved.
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import { gsap } from 'gsap';
import Navbar from '@/layouts/navbar.vue';

definePageMeta({
  layout: "navbar",
});

onMounted(() => {
  gsap.from("header", { duration: 1, y: -50, opacity: 0, ease: "power3.out" });
  gsap.from("main > *", { duration: 1, y: 50, opacity: 0, stagger: 0.2, ease: "power3.out" });
  gsap.from(".testimonial", { duration: 1, y: 50, opacity: 0, stagger: 0.1, ease: "power3.out", scrollTrigger: {
    trigger: ".testimonial",
    start: "top 80%",
  }});
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

body {
  font-family: 'Inter', sans-serif;
}

/* Add any additional custom styles here */
</style>
