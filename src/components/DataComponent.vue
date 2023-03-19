<template>
  <div>
    <h1>{{ msg }}</h1>
    <FormComponent @submit="getForecast" @button="getNightForecast"></FormComponent>
    <!-- <FormComponent @submit="getNightForecast" name="getNightForecast"></FormComponent> -->
    <ForecastComponent :forecast="forecast"></ForecastComponent>
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
      forecast: null
    }
  },
  methods: {

    async getForecast(form) {
      const response = await fetch(`http://localhost:8080/api/date/${form.date}/place/${form.place}`)
      this.forecast = await response.json()
    },

    
    async getNightForecast(form) {
          const response = await fetch(`http://localhost:8080/api/night/date/${form.date}/place/${form.place}`)
          this.forecast = await response.json()
        }
  }
}
</script>
