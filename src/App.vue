<template>
  <img alt="Weather logo" src="./assets/forecast.png">
  <DataComponent msg="Welcome to Forecast App!"/>
</template>

<script>
import DataComponent from './components/DataComponent.vue'

export default {
  name: 'App',
  components: {
    DataComponent
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
