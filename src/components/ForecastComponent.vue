<template>
  <div v-if="forecast">
    <h2>City name: {{ forecast.name }}</h2>
    <p>Phenomenon: {{ forecast.phenomenon }}</p>
    <p>Min temperature: {{ forecast.tempMin || '-' }}</p>
    <p>Max temperature: {{ forecast.tempMax || '-' }}</p>
  </div>
  <div v-else>
    <p>No forecast available</p>
  </div>
</template>

<script>
export default {
  name: 'ForecastComponent',
  props: {
    forecast: Object
  }
}
</script>
