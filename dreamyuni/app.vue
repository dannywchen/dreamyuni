<template>
  <div>
    <Head>
      <Title>Dreamy Uni</Title>
      <Meta name="description" content="Dream the Cream" />
    </Head>

    <NuxtLayout>
      <NuxtPage class="px-[30rem]" />
    </NuxtLayout>
  </div>
</template>

<script setup lang="ts">
useHead({
  script: [{ innerHTML: "console.log('Hello world')" }],
});
</script>
