<!-- @format -->

<template>
  <nav>
    <ul>
      <li><NuxtLink to="/">Main</NuxtLink></li>
      <li><NuxtLink to="/about">About</NuxtLink></li>
      <li><a href="/about">About with a tag</a></li>
    </ul>
  </nav>
</template>

<style>
  ul {
    display: flex;
    gap: 20px;
  }
</style>
