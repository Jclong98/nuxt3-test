<script setup lang="ts">
useSeoMeta({
  titleTemplate: (s) => {
    if (s) {
      return `${s} | Jumoke Media`;
    }

    return "Jumoke Media";
  },
  description:
    "Jumoke is the embodiment and connection between the rich origins of the subject matter and those who capture the beauty to be displayed on an artistic plane.",
});
</script>

<template>
  <NuxtPage />

  <UNotifications />
</template>
