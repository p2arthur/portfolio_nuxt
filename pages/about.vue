<!-- @format -->

<script setup lang="ts">
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
