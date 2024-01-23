<!-- @format -->

<template>
  <div>
    <nav>
      <ul>
        <li><NuxtLink to="/">Logout</NuxtLink></li>
        <li><NuxtLink to="/about">About</NuxtLink></li>
        <li><a href="/about">About with a tag</a></li>
      </ul>
    </nav>
    <slot />
  </div>
</template>
