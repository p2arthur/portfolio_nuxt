<!-- @format -->

<script setup lang="ts">
  useHead({
    titleTemplate: '%s - Arthur Rabelo',
    link: [
      { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css2?family=Roboto:wght@100;700&display=swap',
        crossorigin: '',
      },
    ],
  });
</script>

<template>
  <div class="container mx-auto max-w-2xl">
    <Navbar />
    <slot />
  </div>
</template>

<style>
  body {
    font-family: 'Roboto';
  }

  body {
    @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-100;
  }
</style>
