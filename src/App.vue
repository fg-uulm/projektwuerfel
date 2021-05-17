<template>
  <div id="app">
    <ProjectSpinner msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ProjectSpinner from './components/ProjectSpinner.vue'

export default {
  name: 'App',
  components: {
    ProjectSpinner
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
