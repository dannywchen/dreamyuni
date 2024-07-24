<template>
  <div>
    <h1 class="text-6xl text-center mb-[4rem]">Get A-Head</h1>
    <h2 class="text-2xl text-center">
      In the game of preparing for college by following our 4 year plan
    </h2>

    <div class="grid gap-[1rem] grid-cols-2 mt-10">
      <div class="bg-[#f0f0f0] p-4">
        <h3 class="text-2xl">Freshman</h3>
        <p>Get started on the right foot</p>
      </div>

      <div class="bg-[#f0f0f0] p-4">
        <h3 class="text-2xl">Sophomore</h3>
        <p>Keep the momentum going</p>
      </div>

      <div class="bg-[#f0f0f0] p-4">
        <h3 class="text-2xl">Junior</h3>
        <p>Get ready for the big leagues</p>
      </div>

      <div class="bg-[#f0f0f0] p-4">
        <h3 class="text-2xl">Senior</h3>
        <p>Finish strong</p>
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
