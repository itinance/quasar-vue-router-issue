<script setup lang="ts">

</script>

<template>
  <div>
    <router-link to="/">Home</router-link>
    &nbsp;|&nbsp;
    <router-link :to="{name: 'article', params: {id: 'abc-1'}}">Article 1</router-link>
    &nbsp;|&nbsp;
    <router-link :to="{name: 'article', params: {id: 'abc-2'}}">Article 2</router-link>
    &nbsp;|&nbsp;
    <router-link :to="{name: 'article', params: {id: 'abc-3'}}">Article 3</router-link>
    &nbsp;|&nbsp;
    <router-link :to="{name: 'article', params: {id: 'abc-4'}}">Article 4</router-link>
  </div>

</template>

<style scoped>

</style>
