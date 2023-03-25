<template>
  <div v-if="forecast">
    <p>City name: {{ forecast.name}}</p>
    <p>Day Phenomenon: {{ forecast.dayPhenomenon }}</p>
    <p>Min temperature: {{ forecast.tempMin || '-' }}</p>
    <p>Max temperature: {{ forecast.tempMax || '-' }}</p>
    <p>Info for day: {{dayTextInfo || '-' }}</p>
    <p>Info for night: {{nightTextInfo || '-'}}</p>
  </div>
  <div v-else>
    <p>No forecast available for entered city or date</p>
  </div>
  
</template>
// v-if="forecast"
<script>
export default {
  name: 'ForecastComponent',
  props: {
    forecast: Object,
    dayTextInfo: String,
    nightTextInfo: String
  }
}
</script>
