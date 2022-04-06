<template>
  <dad-jokes />
</template>

<script>
import DadJokes from './components/DadJokes.vue';

export default {
  name: 'App',
  components: {
    DadJokes
  }
}
</script>

<style>
html, body {
  height: 100%;
  background-color: skyblue;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}
</style>
