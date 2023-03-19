<template>
  <form  @submit.prevent="submitForm">
    <label for="date">Date:</label>
    <input id="date" v-model="form.date" type="date">
    <label for="place">Place:</label>
    <input id="place" v-model="form.place" type="text">
    <button type="submit" name="getForecast">Get Day Forecast</button>
    <button type="button" name="getNightForecast" @click="getNightForecast"> Get Night Forecast </button>
  </form>
</template>

<script>
export default {
  name: 'FormComponent',
  data() {
    return {
      form: {
        date: '',
        place: ''
      }
    }
  },
  methods: {
    submitForm() {
      this.$emit('submit', this.form)
    },
    getNightForecast() {
      this.$emit('button', this.form)
    }
  }
}
</script>
