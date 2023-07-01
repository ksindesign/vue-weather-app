<!-- App.vue -->
<template>
  {{ results }}
  <div>{{ results.country }}</div>
  <div>{{ results.cityName }}</div>
  <div>{{ results.temperature }}</div>
  <div>
    <img src="results.icon" alt="icon" />
    <span>{{ results.conditionText }}</span>
  </div>
</template>

<script setup>
const props = defineProps({results: Object})
</script>
