<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white relative overflow-hidden font-playfair">
    <!-- Stars Add More -->
    <div class="absolute inset-0 pointer-events-none">
      <div v-for="i in 50" :key="i" class="absolute animate-twinkle" :style="{ top: `${Math.random() * 100}%`, left: `${Math.random() * 100}%` }">
        <div class="w-1 h-1 bg-white rounded-full"></div>
      </div>
      <div v-for="i in 20" :key="`confetti-${i}`" class="absolute animate-float" :style="{ top: `${Math.random() * 100}%`, left: `${Math.random() * 100}%` }">
        <div class="w-2 h-2 bg-neon-pink rotate-45"></div>
      </div>
    </div>

    <!-- Header Section -->
    <Navbar />

    <!-- Main Banner Section -->
    <main class="text-center py-20 px-4 relative z-10">
      <div class="inline-block bg-gradient-to-r from-pastel-blue to-pastel-purple text-sm px-4 py-2 rounded-full mb-6 animate-pulse">Welcome to DreamyUni</div>
      <h1 class="text-5xl md:text-7xl font-bold mb-6 text-pastel-pink font-cormorant">Choose your dream college.</h1>
      <p class="text-lg mb-8 max-w-2xl mx-auto text-pastel-text font-lato">Unlock direct college tips</p>
      <div class="flex justify-center space-x-4 mb-8">
        <button class="bg-gradient-to-r from-pastel-blue to-pastel-purple text-white px-6 py-3 rounded-full hover:shadow-neon transition duration-300 font-montserrat">Explore Now</button>
        <button class="bg-transparent border-2 border-pastel-pink text-pastel-pink px-6 py-3 rounded-full hover:bg-pastel-pink hover:text-white transition duration-300 font-montserrat">Join Us</button>
      </div>
      <div class="flex justify-center items-center">
        <div class="flex -space-x-2">
          <img v-for="i in 5" :key="i" :src="`https://picsum.photos/40?random=${i}`" :alt="`User ${i}`" class="w-8 h-8 rounded-full border-2 border-pastel-blue">
        </div>
        <span class="ml-2 text-pastel-green font-lato">+99 dreamers</span>
      </div>
    </main>

    <!-- Testimonials Section -->
    <section class="py-20 px-4 overflow-hidden relative z-10">
      <h2 class="text-3xl font-bold text-center mb-2 text-pastel-purple font-cormorant">Dreamer Testimonials</h2>
      <p class="text-center mb-12 text-pastel-text font-lato">Real stories from our community</p>
      <div class="relative">
        <div class="testimonial-row" v-for="(row, index) in 3" :key="index">
          <div class="testimonial-container" :class="{ 'move-right': index % 2 === 0, 'move-left': index % 2 !== 0 }">
            <div v-for="testimonial in testimonials" :key="testimonial.id" class="testimonial-card">
              <div class="flex items-center">
                <img :src="testimonial.avatar" :alt="testimonial.name" class="w-10 h-10 rounded-full mr-3 border-2 border-pastel-green">
                <div>
                  <h3 class="font-bold text-pastel-blue text-xs font-montserrat">{{ testimonial.name }}</h3>
                  <p class="text-xs text-pastel-text font-lato">{{ testimonial.handle }}</p>
                </div>
              </div>
              <p class="text-xs text-pastel-text mt-2 line-clamp-2 font-lato">{{ testimonial.text }}</p>
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

:root {
  --pastel-blue: #a0d2eb;
  --pastel-purple: #d0a5c0;
  --pastel-pink: #ffa5ab;
  --pastel-green: #b8e0d2;
  --pastel-text: #e0e0e0;
}

body {
  font-family: 'Lato', sans-serif;
  background-color: #000000;
  color: var(--pastel-text);
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
  height: 80px;
  margin-bottom: 20px;
  overflow: hidden;
}

.testimonial-container {
  position: absolute;
  display: flex;
  height: 100%;
}

.testimonial-card {
  flex: 0 0 auto;
  width: 220px;
  height: 80px;
  background-color: rgba(28, 28, 28, 0.8);
  border-radius: 8px;
  padding: 10px;
  margin-right: 20px;
  box-shadow: 0 0 10px rgba(160, 210, 235, 0.3);
  transition: all 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 0 20px rgba(208, 165, 192, 0.5);
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
  box-shadow: 0 0 15px rgba(160, 210, 235, 0.7);
}

.bg-pastel-blue { background-color: var(--pastel-blue); }
.bg-pastel-purple { background-color: var(--pastel-purple); }
.bg-pastel-pink { background-color: var(--pastel-pink); }
.bg-pastel-green { background-color: var(--pastel-green); }

.text-pastel-blue { color: var(--pastel-blue); }
.text-pastel-purple { color: var(--pastel-purple); }
.text-pastel-pink { color: var(--pastel-pink); }
.text-pastel-green { color: var(--pastel-green); }
.text-pastel-text { color: var(--pastel-text); }

.border-pastel-blue { border-color: var(--pastel-blue); }
.border-pastel-purple { border-color: var(--pastel-purple); }
.border-pastel-pink { border-color: var(--pastel-pink); }
.border-pastel-green { border-color: var(--pastel-green); }
</style>
