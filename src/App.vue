<template>
  <img alt="Weather logo" src="./assets/weather.png">
  <DataComponent msg="Welcome to Weather App"/>
</template>

<script>
// import FormComponent from './components/FormComponent.vue'
// import ForecastComponent from './components/ForecastComponent.vue'
import DataComponent from './components/DataComponent.vue'

export default {
  name: 'App',
  components: {
    // FormComponent,
    // ForecastComponent,
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
