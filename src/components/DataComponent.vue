<template>
  <div>
    <h1>{{ msg }}</h1>
    <FormComponent  @button="getForecast"></FormComponent>
    <ForecastComponent :forecast="forecast" :dayTextInfo="dayTextInfo" :nightTextInfo="nightTextInfo" ></ForecastComponent>
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
      dayTextInfo: null,
      nightTextInfo: null
    }
  },
  methods: {
    
    async getForecast(form) {
      
          const dayResponse = await fetch(`http://localhost:8080/api/date/${form.date}/place/${form.place}`)  
          const list = await fetch(`http://localhost:8080/api/text/date/${form.date}`)
          const textList = await list.json();
          const dayTextInfo = textList[0]
          const nightTextInfo = textList[1]        
          const forecastDay = await dayResponse.json()

          this.forecast = forecastDay
          this.forecast.dayPhenomenon = forecastDay.phenomenon
          this.dayTextInfo = dayTextInfo
          this.nightTextInfo = nightTextInfo

  }
}
};
</script>
