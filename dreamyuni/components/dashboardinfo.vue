<template>
  <div
    class="w-[30%] my-[2rem] p-4 rounded-md border-[1px] border-gray-300 border-solid"
  >
    <h3 class="text-xl mb-[1rem]">{{ title }}</h3>
    <p class="text-base">
      <span class="font-bold">{{ credits }}</span> Credits
    </p>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  title: string;
  credits: number;
}>();
</script>

<style scoped></style>
