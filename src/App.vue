<template>
  <div style="width: 1800px; height: 800px">
    <!--  <img alt="Vue logo" src="./assets/logo.png">-->
    <!--  <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <deptMap></deptMap>
  </div>
</template>

<script>
import deptMap from './components/deptMap'

export default {
  name: 'App',
  components: {
    deptMap
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
