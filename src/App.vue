<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Replacing data with ref</h1>
  <Data />
</template>

<script>
import Data from './components/Data.vue'

export default {
  name: 'App',
  components: {
    Data
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
