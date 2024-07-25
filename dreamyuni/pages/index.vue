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
      <h2 class="text-3xl font-bold text-center mb-2">Don't take our word for it</h2>
      <p class="text-center mb-12 text-gray-400">Hear what real people have to say about us.</p>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <div class="bg-gray-800 p-6 rounded-lg shadow-lg testimonial">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 rounded-full bg-gradient-to-r from-blue-500 to-green-500 flex items-center justify-center text-white font-bold">MF</div>
            <div class="ml-4">
              <h3 class="font-bold text-white">Marcello Fonseca</h3>
              <p class="text-sm text-gray-400">@Marcello Fonseca</p>
            </div>
          </div>
          <p class="text-white">"Very Nice!! 🔥😲"</p>
        </div>
        <div class="bg-gray-800 p-6 rounded-lg shadow-lg testimonial">
          <div class="flex items-center mb-4">
            <img src="https://placehold.co/40x40" alt="Sayed Suliman" class="w-10 h-10 rounded-full mr-4">
            <div>
              <h3 class="font-bold text-white">Sayed Suliman</h3>
              <p class="text-sm text-gray-400">@Sayed Suliman</p>
            </div>
          </div>
          <p class="text-white">"Can't wait! 😲"</p>
        </div>
        <div class="bg-gray-800 p-6 rounded-lg shadow-lg testimonial">
          <div class="flex items-center mb-4">
            <img src="https://placehold.co/40x40" alt="Danny Chen" class="w-10 h-10 rounded-full mr-4">
            <div>
              <h3 class="font-bold text-white">Danny Chen</h3>
              <p class="text-sm text-gray-400">@Danny Chen</p>
            </div>
          </div>
          <p class="text-white">"That is smooth like butter 🔥"</p>
        </div>
        <div class="bg-gray-800 p-6 rounded-lg shadow-lg testimonial">
          <div class="flex items-center mb-4">
            <img src="https://placehold.co/40x40" alt="Jerome Renard" class="w-10 h-10 rounded-full mr-4">
            <div>
              <h3 class="font-bold text-white">Jerome Renard</h3>
              <p class="text-sm text-gray-400">@Jerome Renard</p>
            </div>
          </div>
          <p class="text-white">"Looking really good!"</p>
        </div>
        <div class="bg-gray-800 p-6 rounded-lg shadow-lg testimonial">
          <div class="flex items-center mb-4">
            <img src="https://placehold.co/40x40" alt="Dally R" class="w-10 h-10 rounded-full mr-4">
            <div>
              <h3 class="font-bold text-white">Dally R</h3>
              <p class="text-sm text-gray-400">@Dally R</p>
            </div>
          </div>
          <p class="text-white">"Great job! Love this. I will go through and provide the feedback."</p>
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
  document.documentElement.classList.add('dark');
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

body {
  font-family: 'Inter', sans-serif;
  background-color: #000000;
  color: #ffffff;
}

/* Add any additional custom styles here */
</style>
