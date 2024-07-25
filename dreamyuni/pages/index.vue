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

    <!-- Footer Section -->
    <footer class="bg-gray-900 py-12 px-4 relative z-10 font-lato">
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
  @apply bg-black text-gray-300;
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
  @apply relative h-20 mb-5 overflow-hidden;
}

.testimonial-container {
  @apply absolute flex h-full;
}

.testimonial-card {
  @apply flex-none w-56 h-20 bg-gray-800 bg-opacity-80 rounded-lg p-2.5 mr-5 shadow-md transition-all duration-300;
}

.testimonial-card:hover {
  @apply transform -translate-y-1 shadow-lg;
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
