<template>
<div>
  <slot></slot>
</div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';
const router = useRouter();

router.afterEach((to, from) => {
  console.log('Router to', to);
  console.log('- from', from);
})
</script>
