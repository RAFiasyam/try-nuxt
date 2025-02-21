<template>
  <div v-if="post">
    <h1 class="text-xl font-bold">{{ post.title }}</h1>
    <p>{{ post.body }}</p>
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>

<script setup>
const route = useRoute();
const { data: post } = await useFetch(`https://jsonplaceholder.typicode.com/posts/${route.params.slug}`);
</script>
