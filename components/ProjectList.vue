<!-- @format -->

<script setup lang="ts">
  interface apiBody {
    stargazers_count: number;
    description: string;
    id: number;
    html_url: string;
    name: string;
  }
  //useFetch will make sure we only fetch once or in the server side or in the client side
  const { data, error, pending } = await useFetch<apiBody[]>(
    'https://api.github.com/users/p2arthur/repos'
  );

  const repos = computed<apiBody[]>(() => {
    if (data.value) {
      data.value
        .filter((repo: apiBody) => repo.description)
        .sort((a, b) => {
          return b.stargazers_count - a.stargazers_count;
        });
      return data.value;
    } else return [];
  });
</script>

<template>
  <h2 class="text-2xl font-semibold mb-10">My Github projects</h2>
  <section v-if="pending"><div>loading</div></section>
  <section v-if="error"><div>error loading data</div></section>
  <section v-if="data">
    <ul class="grid grid-cols-1 gap-4">
      <li
        v-for="repo in repos"
        :key="repo.id">
        <a
          target="_blank"
          :href="repo.html_url"
          ><div class="">
            <div>
              <p class="font-semibold">{{ repo.name }}</p>
              <p>{{ repo.description }}</p>
            </div>
            <p>{{ repo.stargazers_count }} ⭐</p>
          </div></a
        >
      </li>
    </ul>
  </section>
</template>

<style scoped>
  a {
    @apply p-2 border-2 border-gray-500 flex items-center justify-between;
  }
</style>
