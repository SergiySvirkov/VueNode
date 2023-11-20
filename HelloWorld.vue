<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="fetchData">Fetch Data</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      message: 'Hello from Vue!',
    };
  },
  methods: {
    async fetchData() {
      try {
        const response = await axios.get('http://localhost:3000/api/data');
        this.message = response.data.message;
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    },
  },
};
</script>

<style scoped>
/* Your styles here */
</style>

