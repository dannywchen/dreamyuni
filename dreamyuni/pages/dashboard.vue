<template>
  <div class="mt-[3rem] px-[5rem]">
    <header>
      <h1>Hello {{ name }}</h1>
      <p>Manage your portfolio</p>
    </header>

    <div class="flex flex-row justify-between">
      <main class="w-[75%]">
        <div class="flex flex-row justify-between">
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

      <aside class="w-[20%] p-7">
        <h2 class="font-bold">Tasks</h2>
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
