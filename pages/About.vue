<script setup lang="ts">
const title = "About";
const description =
  "This is just a test for Nuxt 3 SEO. This is the about page.";

useSeoMeta({
  title,
  description,
});
</script>

<template>
  <h1 class="text-5xl font-bold">About</h1>

  <p>{{ description }}</p>
</template>
