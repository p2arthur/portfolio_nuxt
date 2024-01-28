<!-- @format -->

<script setup lang="ts">
  const colorMode = useColorMode();
</script>

<template>
  <header
    class="flex justify-between bg-gray-900 items-center p-2 text-gray-100 mb-10">
    <NuxtLink
      to="/"
      class="text-xl"
      >Arthur Rabelo</NuxtLink
    >

    <nav>
      <ul class="flex gap-10 p-5 font-mono">
        <li class="link">
          <NuxtLink to="/">Main</NuxtLink>
        </li>
        <li class="link">
          <NuxtLink to="/about">About</NuxtLink>
        </li>
        <li class="link">
          <NuxtLink to="/projects">Projects</NuxtLink>
        </li>
        <ClientOnly>
          <div>
            <ColorMode />
          </div>
        </ClientOnly>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
  .dark header {
  }
  .link {
    @apply p-2 hover:bg-gray-500;
  }
</style>
