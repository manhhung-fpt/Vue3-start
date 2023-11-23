<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { createApp, ref, onMounted } from 'vue'

const count = ref(0);
function increment() {
  count.value++;
}
onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})
</script>

<script>
export default {
  data() {
    return {
      count: 0,
      buttonColor: 'red', // Initial color is set to red
    };
  },
  methods: {
    increment() {
      this.count++;
    },
  },
};
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>

  <div id="app">
    <button @click="increment" v-bind:style="{ backgroundColor: buttonColor }">Đếm: {{ count }}</button>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
