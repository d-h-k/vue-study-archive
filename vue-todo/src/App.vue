<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg-value="Welcome to Your Vue.js App"/>
    <hr>
    <mydiv title="my div title" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import mydiv from './components/mydiv.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    mydiv
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
