<template>
  <q-page class="">
    <LinkCatcherComponent>
      <div class="row items-center justify-evenly">
        <NavComponent></NavComponent>
      </div>
      <div class="row items-center justify-evenly">
        <HomeComponent
          active
        ></HomeComponent>
      </div>
    </LinkCatcherComponent>

  </q-page>
</template>

<script setup lang="ts">
import HomeComponent from 'components/HomeComponent.vue';
import NavComponent from 'components/NavComponent.vue';
import LinkCatcherComponent from 'components/LinkCatcherComponent.vue';

defineOptions({
  name: 'IndexPage'
});

</script>
