<template>
  <div class="container mx-auto py-20">
    <div class="bg-white rounded-lg shadow-lg p-10">
      <h1 class="text-4xl font-bold mb-6 text-center">About Us</h1>
      <p class="text-lg leading-relaxed mb-6 text-center">
        Dreamy Uni is a platform that provides online courses for students who
        want to learn new skills. We offer a wide range of courses that are
        designed to help you learn new skills and improve your career.
      </p>
      <div class="flex justify-center">
        <img
          src="../public/Monkey-Selfie.webp"
          alt="danny selfie"
          class="rounded-full shadow-lg w-64 h-64 object-cover"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "navbar",
});
</script>

<style scoped></style>
