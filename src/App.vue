<!-- App.vue -->
<template>
  <Title />
  <Form @submit-form="getWeather" />
  <Results />
</template>

<script setup>
import {reactive} from 'vue'
import axios from 'axios'
import Title from './components/Title.vue'
import Form from './components/Form.vue'
import Results from './components/Results.vue'

// データの保管
const results = reactive({
  country: '',
  cityName: '',
  temperature: '',
  icon: '',
})

const getWeather = () => {
  axios
    .get(
      'https://api.weatherapi.com/v1/current.json?key=b480752178fd4b3f99f00123230107&q=London&aqi=no'
    )
    .then((res) => {
      ;(results.country = res.data.location.country),
        (results.cityName = res.data.location.name),
        (results.temperature = res.data.current.temp_c),
        (results.conditionText = res.data.current.condition.text),
        (results.icon = res.data.current.condition.icon)
    })
}
</script>
