<template>
  <div class="mt-[3rem] px-[5rem]">
    <header class="pb-[1.25rem] border-b-[2px] border-b-gray-200 border-solid">
      <h1 class="font-bold text-3xl">Essay Manager</h1>
      <p class="text-lg text-gray-500 mt-[1rem]">
        Organize, manage & write all your college essays all in one place
      </p>
    </header>

    <main>
      <p class="text-lg text-gray-500 mt-[1rem]">
        Note: Some colleges may no have pre-filled prompts, so you can add them
        manually. All pre-filled prompts are from the 2024-2025 cycle.
      </p>

      <div class="flex flex-col gap-2 mt-[0.75rem]">
        <div
          class="flex flex-row justify-between items-center p-[1rem] rounded-xl border-[1px] border-gray-300 border-solid"
        >
          <div class="flex flex-row">
            <img
              src="/assets/commonappicon.webp"
              alt=""
              class="h-[4.5rem] mr-[1rem] rounded-2xl"
            />
            <div>
              <h3 class="font-bold text-xl">
                Common App Essay / Personal Statement
              </h3>
              <p class="text-lg text-gray-500">Drafts: 0</p>
            </div>
          </div>
          <button
            class="h-[2.5rem] px-[1.5rem] bg-blue-500 rounded-lg border-[1px] border-gray-300 border-solid"
          >
            Manage
          </button>
        </div>

        <div
          class="flex flex-row justify-between items-center p-[1rem] rounded-xl border-[1px] border-gray-300 border-solid"
          v-for="(item, index) in list"
          :key="index"
        >
          <div class="flex flex-row">
            <img
              src="/assets/commonappicon.webp"
              alt=""
              class="h-[4.5rem] mr-[1rem] rounded-2xl"
            />
            <div>
              <h3 class="font-bold text-xl">
                {{ item.name }}
              </h3>
              <p class="text-lg text-gray-500">Drafts: {{ item.drafts }}</p>
            </div>
          </div>
          <button
            class="h-[2.5rem] px-[1.5rem] bg-blue-500 rounded-lg border-[1px] border-gray-300 border-solid"
          >
            Manage
          </button>
        </div>
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
const list = ref([
  {
    name: "Harvard University",
    drafts: 0,
  },
  {
    name: "Massachusetts Institute of Technology",
    drafts: 0,
  },
]);

definePageMeta({
  layout: "navbar",
});
</script>

<style scoped></style>
