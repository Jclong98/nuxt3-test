<script setup lang="ts"></script>

<template>
  <div>
    <nav class="p-4">
      <ul class="flex gap-4">
        <li>
          <ULink to="/" active-class="text-primary">Home</ULink>
        </li>
        <li>
          <ULink to="/about" active-class="text-primary">about</ULink>
        </li>
      </ul>
    </nav>

    <main class="p-4">
      <NuxtPage />
    </main>

    <UNotifications />
  </div>
</template>
