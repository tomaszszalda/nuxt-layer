

<template>
  <div>
    <h1>promo</h1>
<!--    <pre>{{ home }}</pre>-->
    <ContentRenderer v-if="home" :value="home" />
  </div>
</template>

<script setup lang="ts">
const { data: home } = await useAsyncData(() => queryCollection('content').path('/en/promotions').first())
console.log('home', home.value);
useSeoMeta({
  title: home.value?.title,
  description: home.value?.description
})
</script>
