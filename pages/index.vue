<script setup lang="ts">
const title = "Home";
const description =
  "This is just a test for Nuxt 3 SEO. This is the home page.";

useSeoMeta({
  title,
  description,
});
</script>

<template>
  <h1 class="text-5xl font-bold">Home</h1>

  <p>{{ description }}</p>
</template>
