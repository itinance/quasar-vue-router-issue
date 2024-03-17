# Quasar App (quasar-project)

A Quasar Project

## Install the dependencies
```bash
yarn
# or
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)
```bash
quasar dev
```


#      Explaining the issue with router:

The IndexPage is encapsulated into the <b>LinkCatcherComponent</b>.
This component listens on the router via "afterEach":


    import { useRouter } from 'vue-router';
    const router = useRouter();

    router.afterEach((to, from) => {
    console.log('Router to', to);
    console.log('- from', from);


While navigating through the Links in the <b>NavComponent</b>, everything works as expected:
we move from Article 1 to Article 2 to Article 3 and back and on every transition, we
see the console logs from the LinkCatcherComponent.

However, as soon as we press the Button "go to article with push", the router logs are happening twice.
Because `router.afterEach` will get executed twice.

    const gotoArticle = () => {
    router.push({ name: 'article', params: { id: 'goto-test' } });

After pressing a third time on the button, the logs from the router-event will happen 3x times with every
single transition from one article to another. Number counting with every next click on the button using `router.push`.

