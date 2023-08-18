<template>
  <div
    v-if="!pending"
    v-text="data"
  />
  <div
    v-else
    v-text="'loading'"
  />
</template>

<script setup>
const { data: cachedData } = useNuxtData('test-key');

const { data, pending } = await useFetch('https://jsonplaceholder.typicode.com/todos/1', {
  key: 'test-key',
  server: false,
});
</script>
