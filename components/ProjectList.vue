<!-- @format -->

<script setup lang="ts">
  //useFetch will make sure we only fetch once or in the server side or in the client side
  const { data, error, pending } = await useFetch(
    'https://api.github.com/users/p2arthur/repos'
  );
</script>

<template>
  <section v-if="pending"><div>loading</div></section>
  <section v-if="error"><div>error loading data</div></section>
  <section v-if="data">
    <div>{{ data }}</div>
  </section>
</template>
