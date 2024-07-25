<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white relative overflow-hidden font-playfair">
    <!-- Stars and Confetti -->
    <div class="absolute inset-0 pointer-events-none">
      <div v-for="i in 50" :key="i" class="absolute animate-twinkle" :style="{ top: `${Math.random() * 100}%`, left: `${Math.random() * 100}%` }">
        <div class="w-1 h-1 bg-white rounded-full"></div>
      </div>
      <div v-for="i in 20" :key="`confetti-${i}`" class="absolute animate-float" :style="{ top: `${Math.random() * 100}%`, left: `${Math.random() * 100}%` }">
        <div class="w-2 h-2 bg-pink-400 rotate-45"></div>
      </div>
    </div>

    <!-- Header Section -->
    <Navbar />

    <!-- Main Banner Section -->
    <main class="text-center py-20 px-4 relative z-10">
      <div class="inline-block bg-gradient-to-r from-blue-300 to-purple-300 text-sm px-4 py-2 rounded-full mb-6 animate-pulse">Welcome to DreamyUni</div>
      <h1 class="text-5xl md:text-7xl font-bold mb-6 text-pink-300 font-cormorant">Choose your dream college.</h1>
      <p class="text-lg mb-8 max-w-2xl mx-auto text-gray-300 font-lato">Unlock direct college tips</p>
      <div class="flex justify-center space-x-4 mb-8">
        <button class="bg-gradient-to-r from-blue-300 to-purple-300 text-white px-6 py-3 rounded-full hover:shadow-neon transition duration-300 font-montserrat">Explore Now</button>
        <button class="bg-transparent border-2 border-pink-300 text-pink-300 px-6 py-3 rounded-full hover:bg-pink-300 hover:text-white transition duration-300 font-montserrat">Join Us</button>
      </div>
      <div class="flex justify-center items-center">
        <div class="flex -space-x-2">
          <img v-for="i in 5" :key="i" :src="`https://picsum.photos/40?random=${i}`" :alt="`User ${i}`" class="w-8 h-8 rounded-full border-2 border-blue-300">
        </div>
        <span class="ml-2 text-green-300 font-lato">+99 dreamers</span>
      </div>
    </main>

    <!-- Testimonials Section -->
    <section class="py-20 px-4 overflow-hidden relative z-10">
      <h2 class="text-3xl font-bold text-center mb-2 text-purple-300 font-cormorant">Dreamer Testimonials</h2>
      <p class="text-center mb-12 text-gray-300 font-lato">Real stories from our community</p>
      <div class="relative">
        <div class="testimonial-row" v-for="(row, index) in 3" :key="index">
          <div class="testimonial-container" :class="{ 'move-right': index % 2 === 0, 'move-left': index % 2 !== 0 }">
            <div v-for="testimonial in testimonials" :key="testimonial.id" class="testimonial-card">
              <div class="flex items-center">
                <img :src="testimonial.avatar" :alt="testimonial.name" class="w-10 h-10 rounded-full mr-3 border-2 border-green-300">
                <div>
                  <h3 class="font-bold text-blue-300 text-xs font-montserrat">{{ testimonial.name }}</h3>
                  <p class="text-xs text-gray-300 font-lato">{{ testimonial.handle }}</p>
                </div>
              </div>
              <p class="text-xs text-gray-300 mt-2 line-clamp-2 font-lato">{{ testimonial.text }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Bento Box Section -->
    <section class="py-20 px-4 relative z-10">
      <h2 class="text-3xl font-bold text-center mb-12 text-purple-300 font-cormorant">Explore DreamyUni</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div class="bg-gray-800 bg-opacity-80 rounded-lg p-6 shadow-lg hover:shadow-xl transition-all duration-300">
          <h3 class="text-xl font-bold mb-4 text-blue-300 font-montserrat">College Finder</h3>
          <p class="text-gray-300 font-lato mb-4">Discover your perfect college match with our advanced search tool.</p>
          <button class="bg-blue-300 text-gray-900 px-4 py-2 rounded-full hover:bg-blue-400 transition duration-300 font-montserrat">Start Searching</button>
        </div>
        <div class="bg-gray-800 bg-opacity-80 rounded-lg p-6 shadow-lg hover:shadow-xl transition-all duration-300 md:row-span-2">
          <h3 class="text-xl font-bold mb-4 text-pink-300 font-montserrat">Application Tracker</h3>
          <p class="text-gray-300 font-lato mb-4">Stay organized and never miss a deadline with our comprehensive application tracker.</p>
          <div class="bg-gray-700 rounded-lg p-4 mb-4">
            <h4 class="text-lg font-semibold mb-2 text-white font-montserrat">Upcoming Deadlines</h4>
            <ul class="text-gray-300 font-lato">
              <li>Harvard University - Dec 1</li>
              <li>Stanford University - Jan 5</li>
              <li>MIT - Jan 15</li>
            </ul>
          </div>
          <button class="bg-pink-300 text-gray-900 px-4 py-2 rounded-full hover:bg-pink-400 transition duration-300 font-montserrat">View My Applications</button>
        </div>
        <div class="bg-gray-800 bg-opacity-80 rounded-lg p-6 shadow-lg hover:shadow-xl transition-all duration-300">
          <h3 class="text-xl font-bold mb-4 text-green-300 font-montserrat">Essay Workshop</h3>
          <p class="text-gray-300 font-lato mb-4">Craft compelling essays with our guided workshops and expert feedback.</p>
          <button class="bg-green-300 text-gray-900 px-4 py-2 rounded-full hover:bg-green-400 transition duration-300 font-montserrat">Start Writing</button>
        </div>
        <div class="bg-gray-800 bg-opacity-80 rounded-lg p-6 shadow-lg hover:shadow-xl transition-all duration-300">
          <h3 class="text-xl font-bold mb-4 text-yellow-300 font-montserrat">Scholarship Finder</h3>
          <p class="text-gray-300 font-lato mb-4">Uncover scholarship opportunities tailored to your unique profile.</p>
          <button class="bg-yellow-300 text-gray-900 px-4 py-2 rounded-full hover:bg-yellow-400 transition duration-300 font-montserrat">Find Scholarships</button>
        </div>
      </div>
    </section>

    <!-- Footer Section -->
    <footer class="bg-gray-900 py-12 px-4 relative z-10 font-lato">
      <div class="max-w-6xl mx-auto flex flex-wrap justify-between">
        <div class="w-full md:w-1/4 mb-8 md:mb-0">
          <h4 class="text-xl font-bold mb-4 text-purple-300">DreamyUni</h4>
          <p class="text-gray-400">Empowering students to achieve their college dreams.</p>
        </div>
        <div class="w-full md:w-1/4 mb-8 md:mb-0">
          <h4 class="text-lg font-semibold mb-4 text-blue-300">Quick Links</h4>
          <ul class="text-gray-400">
            <li class="mb-2"><a href="#" class="hover:text-white transition duration-300">Home</a></li>
            <li class="mb-2"><a href="#" class="hover:text-white transition duration-300">About Us</a></li>
            <li class="mb-2"><a href="#" class="hover:text-white transition duration-300">Services</a></li>
            <li class="mb-2"><a href="#" class="hover:text-white transition duration-300">Contact</a></li>
          </ul>
        </div>
        <div class="w-full md:w-1/4 mb-8 md:mb-0">
          <h4 class="text-lg font-semibold mb-4 text-pink-300">Contact Us</h4>
          <p class="text-gray-400 mb-2">123 Dream Street, College Town, ST 12345</p>
          <p class="text-gray-400 mb-2">Phone: (123) 456-7890</p>
          <p class="text-gray-400">Email: info@dreamyuni.com</p>
        </div>
        <div class="w-full md:w-1/4">
          <h4 class="text-lg font-semibold mb-4 text-green-300">Follow Us</h4>
          <div class="flex space-x-4">
            <a href="#" class="text-gray-400 hover:text-white transition duration-300">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition duration-300">
              <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition duration-300">
              <i class="fab fa-instagram"></i>
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition duration-300">
              <i class="fab fa-linkedin-in"></i>
            </a>
          </div>
        </div>
      </div>
      <div class="mt-8 text-center text-gray-400">
        <p>&copy; 2023 DreamyUni. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import { gsap } from 'gsap';
import Navbar from '@/layouts/navbar.vue';

definePageMeta({
  layout: "navbar",
});

const testimonials = ref([
  { id: 1, name: "Marcello F.", handle: "@MarcelloF", text: "Mind-blowing courses! 🚀", avatar: "https://picsum.photos/40?random=1" },
  { id: 2, name: "Sayed S.", handle: "@SayedS", text: "Can't wait for more! 🎓", avatar: "https://picsum.photos/40?random=2" },
  { id: 3, name: "Danny C.", handle: "@DannyC", text: "Smooth learning experience 👌", avatar: "https://picsum.photos/40?random=3" },
  { id: 4, name: "Jerome R.", handle: "@JeromeR", text: "Top-notch content!", avatar: "https://picsum.photos/40?random=4" },
  { id: 5, name: "Dally R.", handle: "@DallyR", text: "Innovative approach to education", avatar: "https://picsum.photos/40?random=5" },
]);

onMounted(() => {
  gsap.from("header", { duration: 1, y: -50, opacity: 0, ease: "power3.out" });
  gsap.from("main > *", { duration: 1, y: 50, opacity: 0, stagger: 0.2, ease: "power3.out" });
  
  gsap.to(".move-right", {
    xPercent: -100,
    repeat: -1,
    duration: 20,
    ease: "linear",
  });

  gsap.to(".move-left", {
    xPercent: 100,
    repeat: -1,
    duration: 20,
    ease: "linear",
  });

  document.documentElement.classList.add('dark');
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Cormorant+Garamond:wght@400;700&family=Lato:wght@400;700&family=Montserrat:wght@400;700&display=swap');

body {
  font-family: 'Lato', sans-serif;
  background-color: black;
  color: #d1d5db;
}

.font-playfair {
  font-family: 'Playfair Display', serif;
}

.font-cormorant {
  font-family: 'Cormorant Garamond', serif;
}

.font-lato {
  font-family: 'Lato', sans-serif;
}

.font-montserrat {
  font-family: 'Montserrat', sans-serif;
}

.testimonial-row {
  position: relative;
  height: 5rem;
  margin-bottom: 1.25rem;
  overflow: hidden;
}

.testimonial-container {
  position: absolute;
  display: flex;
  height: 100%;
}

.testimonial-card {
  flex: none;
  width: 14rem;
  height: 5rem;
  background-color: rgba(31, 41, 55, 0.8);
  border-radius: 0.5rem;
  padding: 0.625rem;
  margin-right: 1.25rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  transition: all 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-0.25rem);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.move-right {
  animation: moveRight 20s linear infinite;
}

.move-left {
  animation: moveLeft 20s linear infinite;
}

@keyframes moveRight {
  0% { transform: translateX(0); }
  100% { transform: translateX(-100%); }
}

@keyframes moveLeft {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(0); }
}

.animate-twinkle {
  animation: twinkle 4s infinite;
}

@keyframes twinkle {
  0%, 100% { opacity: 0; }
  50% { opacity: 1; }
}

.animate-float {
  animation: float 6s infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px) rotate(45deg); }
}

.shadow-neon {
  @apply shadow-lg shadow-blue-300;
}
</style>
