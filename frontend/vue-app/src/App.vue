<template>
  <div class="container">
    <h1>Vue + .NET API (Docker!)</h1>
    <button @click="loadData" :disabled="loading">Pobierz pogodę</button>

    <div v-if="loading">Ładowanie...</div>

    <ul v-if="weather.length">
      <li v-for="item in weather" :key="item.date">
        {{ item.date }}: {{ item.temperatureC }}°C – {{ item.summary }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      weather: [],
      loading: false
    }
  },
  methods: {
    async loadData() {
      this.loading = true
      try {
        const res = await axios.get('/api/weatherforecast')
        this.weather = res.data
      } catch (err) {
        alert('Błąd: ' + err.message)
      } finally {
        this.loading = false
      }
    }
  }
}
</script>

<style>
.container {
  max-width: 600px;
  margin: 40px auto;
  font-family: Arial, sans-serif;
  text-align: center;
}
button {
  margin: 20px;
  padding: 10px 20px;
  font-size: 16px;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin: 10px 0;
  font-size: 18px;
}
</style>