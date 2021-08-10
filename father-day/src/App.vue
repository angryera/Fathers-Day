<template>
  <div id="app">
    <StartPanel msg="Father's Day"/>
  </div>
</template>

<script>
import StartPanel from './components/StartPanel.vue'

export default {
  name: 'App',
  components: {
    StartPanel
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
