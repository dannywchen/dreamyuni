<template>
  <div class="w-full mb-[2rem] py-[2rem] border-solid border-black border-b-2">
    <nav>
      <ul class="flex justify-center gap-4">
        <li>
          <nuxt-link to="/">Dreamy Uni</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">About Us</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Sign Up</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Courses</nuxt-link>
        </li>
      </ul>
    </nav>
  </div>

  <slot />
</template>

<script setup lang="ts"></script>

<style scoped></style>
