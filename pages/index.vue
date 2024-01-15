<script setup lang="ts">
const toast = useToast();

const email = ref("");
const loading = ref(false);

async function onSubmit() {
  loading.value = true;

  try {
    const res = await $fetch("/api/subscribe", {
      method: "POST",
      body: JSON.stringify({ email: email.value }),
    });

    console.log(res);

    email.value = "";

    toast.add({
      color: "green",
      title: "Nice!",
      description: "You're now subscribed to our newsletter!",
    });
  } catch (error) {
    toast.add({
      color: "red",
      title: "Uh oh!",
      description: "Something went wrong. Please try again later.",
    });
  } finally {
    loading.value = false;
  }
}

const submitButtonIsDisabled = computed(() => !email.value || loading.value);
</script>

<template>
  <div class="min-h-dvh flex items-center justify-center bg-neutral-900">
    <div class="flex flex-col gap-6 p-4 max-w-2xl">
      <h1 class="text-5xl font-bold text-center">Jumoke Media</h1>

      <p class="text-center">
        <strong class="text-primary">Jumoke</strong> is the embodiment and
        connection between the
        <strong class="text-primary">rich origins</strong> of the subject matter
        and those who capture the
        <strong class="text-primary">beauty</strong> to be displayed on an
        artistic plane.
      </p>

      <p class="text-center">
        This newsletter will focus on gatherings that capture the beauty of
        <strong class="text-primary">automotive culture</strong>. Subscribe for
        event coverage and schedules.
      </p>

      <form
        class="grid sm:grid-cols-[1fr_auto] gap-2"
        @submit.prevent="onSubmit"
      >
        <UInput
          aria-label="email"
          placeholder="email@example.com"
          v-model="email"
          type="email"
        ></UInput>

        <div class="flex justify-center">
          <UButton
            type="submit"
            :disabled="submitButtonIsDisabled"
            :loading="loading"
            block
          >
            Sign Up
          </UButton>
        </div>
      </form>
    </div>
  </div>
</template>
