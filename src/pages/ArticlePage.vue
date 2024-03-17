<script setup lang="ts">

import NavComponent from 'components/NavComponent.vue';
import { useRoute } from 'vue-router';
import { ref, watch } from 'vue';

const route = useRoute();

const id = ref('');

watch(() => route.params.id, (_id) => {
  console.log('id changed to', _id);
  id.value = _id as string;
}, { immediate: true });


</script>

<template>
  <div>
    <NavComponent></NavComponent>
    <h1>Article {{ id }}</h1>
    <p>

      Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's
      <a href="/standard">standard</a> dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a
      type specimen book. It has survived not only five <a href="/centuries">centuries</a>, but also the leap into electronic typesetting,
      remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing
      Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions
      of Lorem Ipsum.
    </p>
  </div>
</template>

<style scoped>

</style>
