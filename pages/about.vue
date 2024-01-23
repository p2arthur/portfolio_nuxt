<!-- @format -->

<script setup lang="ts">
  useSeoMeta({
    title: 'About page',
    description: 'This is the main page of the portfolio website',
    ogTitle: 'Main page',
  });

  const enableCustomLayout = () => {
    setPageLayout('logged');
  };
</script>

<template>
  <div>
    <h1>This is an about page</h1>
    <button @click="enableCustomLayout">Change layout</button>
  </div>
</template>
