<template>
  <div class="mt-[3rem] px-[5rem] h-full">
    <header class="pb-[1.25rem] border-b-[2px] border-b-gray-200 border-solid">
      <h1 class="font-bold text-3xl">Hello {{ name }}</h1>
      <p class="text-lg mt-[1rem]">Manage your college journey below :)</p>
    </header>

    <div class="flex flex-row justify-between h-100vh">
      <main class="w-[70%]">
        <div class="flex flex-row justify-between py-[3rem]">
          <Dashboardinfo
            v-for="(item, index) in data"
            :key="index"
            :title="item.title"
            :credits="item.credits"
          />
        </div>

        <h2>Upcoming Deadlines</h2>
        <p>
          List of colleges you are applying to. Add or remove colleges in the
          college tracker.
        </p>
      </main>

      <aside class="w-[27.5%] p-[3rem] bg-gray-300">
        <h2 class="text-xl font-semibold mb-1">Tasks</h2>
        <p class="text-gray-700">Upcoming tasks in the roadmap.</p>
      </aside>
    </div>
  </div>
</template>

<script setup lang="ts">
const name = ref("Danny Wen-Bin Chen");
const data = ref([
  {
    title: "Essays",
    credits: 0,
  },
  {
    title: "Application evaluations",
    credits: 0,
  },
  {
    title: "Colleges / Supplementals",
    credits: 0,
  },
]);

definePageMeta({
  layout: "navbar",
});
</script>

<style scoped></style>
