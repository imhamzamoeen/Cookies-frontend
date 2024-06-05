<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <cookie-check></cookie-check>
</template>

<script>
import cookieCheck from './components/cookieCheck.vue'


export default {
  name: 'App',
  components: {
    cookieCheck,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
