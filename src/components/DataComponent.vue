<template>
  <div>
    <h1>{{ msg }}</h1>
    <FormComponent @submit="getForecast" @button="getNightForecast"></FormComponent>
    <!-- <FormComponent @submit="getNightForecast" name="getNightForecast"></FormComponent> -->
    <ForecastComponent :forecast="forecast" :averageTemp="averageTemp"></ForecastComponent>
  </div>
</template>

<script>
import FormComponent from './FormComponent.vue'
import ForecastComponent from './ForecastComponent.vue'

export default {
  name: 'DataComponent',
  components: {
    FormComponent,
    ForecastComponent
  },
  props: {
    msg: String
  },
  data() {
    return {
      forecast: null,
      averageTemp: null
    }
  },
  methods: {

    async getForecast(form) {
      const response = await fetch(`http://localhost:8080/api/date/${form.date}/place/${form.place}`)
      const response1 = await fetch(`http://localhost:8080/api/average/date/${form.date}`)
      // this.forecast = await response.json()
      // this.averageTemp = await response1.json()

      const forecast = await response.json()
      const averageTemp = await response1.text()
      this.forecast = forecast
      this.averageTemp = averageTemp
    },

    
    async getNightForecast(form) {
          const response = await fetch(`http://localhost:8080/api/night/date/${form.date}/place/${form.place}`)
          this.forecast = await response.json()
        }
  }
}
</script>
