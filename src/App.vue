<template>
  <!-- <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
  <img id="vue-logo" alt="Vue logo" src="./assets/logo.png" />
  <Header />
  <div class="container">
    <router-view />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
export default {
  components: {
    Header,
  },
};
</script>

<style>
#vue-logo {
  height: 7vmin;
  right: 0;
  bottom: 0;
  position: fixed;
}
</style>
