<!-- @format -->

<script setup lang="ts">
  const route = useRoute();
  console.log(route.params.slug);
</script>

<template>
  <h1>
    We're inside of blog post number <span>{{ route.params.slug }}</span>
  </h1>
</template>
