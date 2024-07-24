<template>
  <div
    class="w-full mb-[2rem] px-[30rem] py-[2rem] border-solid border-gray border-b-[1px]"
  >
    <nav>
      <ul class="flex flex-row justify-between items-center">
        <li class="text-2xl">
          <nuxt-link to="/">Dreamy Uni</nuxt-link>
        </li>
        <div class="flex gap-10">
          <li>
            <nuxt-link to="/aboutus">About Us</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/signup">Sign Up </nuxt-link>
          </li>
          <li>
            <nuxt-link to="courses">Courses</nuxt-link>
          </li>
        </div>
      </ul>
    </nav>
  </div>

  <slot />
</template>

<script setup lang="ts">
const router = useRouter();
</script>

<style scoped></style>
