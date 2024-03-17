<template>
  <div>
    <p>Home Component</p>

    <router-link to="/">Home</router-link>
    <router-link :to="{name: 'article', params: {id: 'abc-1'}}">Article ABC-1</router-link>

    <q-btn @click="gotoArticle" label="Go to article with push" />

    <br><br><br>
    <h1>
      Explaining the issue with router:
    </h1><p>
    The IndexPage is encapsulated into the <b>LinkCatcherComponent</b>.
    This component listens on the router via "afterEach":
  </p>
    <pre>
import { useRouter } from 'vue-router';
const router = useRouter();

router.afterEach((to, from) => {
  console.log('Router to', to);
  console.log('- from', from);
})

    </pre>

    <p>
      While navigating through the Links in the <b>NavComponent</b>, everything works as expected:
      we move from Article 1 to Article 2 to Article 3 and back and on every transition, we
      see the console logs from the LinkCatcherComponent.
    </p>
    <p>
      However, as soon as we press the Button "go to article with push", the router logs are happening twice.
      Because `router.afterEach` will get executed twice.
    </p>
    <pre>
const gotoArticle = () => {
  router.push({ name: 'article', params: { id: 'goto-test' } });
}
    </pre>
    <p>
      After pressing a third time on the button, the logs from the router-event will happen 3x times with every
      single transition from one article to another. Number counting with every next click on the button using `router.push`.
    </p>

  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';

const router = useRouter();

const gotoArticle = () => {
  router.push({ name: 'article', params: { id: 'goto-test' } });
}
</script>

<style>
h1 {
  font-size: 22px;
  font-weight: bold;
}

p {
  font-size: 16px;
}
</style>
