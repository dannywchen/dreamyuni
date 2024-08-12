<template>
  <div class="mt-[3rem] px-[5rem]">
    <header class="pb-[1.25rem] border-b-[2px] border-b-gray-200 border-solid">
      <h1 class="font-bold text-3xl">College Tracker</h1>

      <div class="flex flex-row justify-between">
        <p class="text-lg text-gray-500 mt-[1rem]">
          Efficiently organize and track your college applications all in one
          place.
        </p>

        <p class="text-lg text-blue-600 underline mt-[1rem]">
          <a href="" target="_blank" rel="noopener noreferrer"
            >Share your list</a
          >
        </p>
      </div>
    </header>

    <main class="mt-[2rem]">
      <div class="flex flex-row-reverse gap-6">
        <button
          class="p-[0.75rem] rounded-lg border-[1px] border-gray-300 border-solid"
        >
          <img src="" alt="" />
          Delete Selected Colleges
        </button>
        <button
          class="p-[0.75rem] rounded-lg border-[1px] border-gray-300 border-solid"
        >
          <img src="" alt="" />
          Add Column
        </button>
        <button
          class="p-[0.75rem] rounded-lg border-[1px] border-gray-300 border-solid"
        >
          <img src="" alt="" />
          Columns
        </button>
        <button
          class="p-[0.75rem] rounded-lg border-[1px] border-gray-300 border-solid"
        >
          <img src="" alt="" />
          Analyze Colleges
        </button>
        <button
          class="p-[0.75rem] rounded-lg border-[1px] border-gray-300 border-solid"
        >
          <img src="" alt="" />
          Add College
        </button>
      </div>

      <div>
        <table class="w-full mt-[2rem]">
          <thead>
            <tr>
              <th class="border-b-[1px] border-gray-300 border-solid">
                <input type="checkbox" v-if="colleges.length != 0" />
              </th>
              <th
                class="p-0 border-b-[1px] border-gray-300 border-solid"
                v-for="(item, index) in header"
                :key="index"
              >
                {{ item }}
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, index) in colleges" :key="index">
              <th class="border-b-[1px] border-gray-300 border-solid">
                <input type="checkbox" />
              </th>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.CollegeName }}
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                <button>Manage</button>
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.ApplicationDeadline }}
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.Type }}
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.EssayProgress }}
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.Analysis }}
              </td>
              <td class="p-[1rem] border-[1px] border-gray-300 border-solid">
                {{ item.Decision }}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
import type { CollegeTrackerInfo } from "~/assets/interfaces/data-formats";

const header = ref<Array<string>>([
  "College Name",
  "Supplemental Essay",
  "Application Deadline",
  "Type",
  "Essay Progress",
  "Analysis",
  "Decision",
]);

const colleges = ref<Array<CollegeTrackerInfo>>([
  /* {
    CollegeName: "Harvard University",
    ApplicationDeadline: "January 4th, 2025",
    Type: "RD",
    EssayProgress: "Submitted",
    Analysis: "Not Analyzed",
    Decision: "Not Applied Yet",
  },
  {
    CollegeName: "Massachusetts Institute of Technology",
    ApplicationDeadline: "January 3rd, 2025",
    Type: "ED",
    EssayProgress: "Submitted",
    Analysis: "Good",
    Decision: "Accepted",
  }, */
]);

definePageMeta({
  layout: "navbar",
});
</script>

<style scoped></style>
