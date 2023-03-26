<template>
  <form  @submit.prevent="submitForm">
    <label for="date">Date:</label>
    <input id="date" v-model="form.date" type="date">
    <label for="place">Place:</label>
    <input id="place" v-model="form.place" type="text">
    <button type="button" name="getForecast" @click="getForecast"> Get Forecast </button>
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
    getForecast() {
      this.$emit('button', this.form)
    }
  }
}
</script>
