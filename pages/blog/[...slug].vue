<!-- @format -->

<script setup lang="ts">
  const route = useRoute();
  console.log(route.params.slug);
</script>

<template>
  <article><ContentDoc /></article>
</template>
