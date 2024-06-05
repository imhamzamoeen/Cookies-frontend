<template>
  <div>
    <button @click="setCookie">Set Cookie</button>
    <button @click="getCookies">get Cookie</button>

    <h1>checking components </h1>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  methods: {
    async setCookie() {
      try {
        // Make an Axios request to the backend route
        axios.defaults.withCredentials = true;

        const response = await axios.get('https://cookie-backend.test/set-cookie');

        // Check if the response was successful
        if (response.status === 200) {
          // Log a success message
          console.log('Cookie has been set successfully!');
        } else {
          // Log an error message if the response was not successful
          console.error('Failed to set cookie:', response.statusText);
        }
      } catch (error) {
        // Log any errors that occur during the request
        console.error('An error occurred while setting cookie:', error.message);
      }
    },
    async getCookies() {
      try {
        // Set axios defaults to include credentials with requests
        axios.defaults.withCredentials = true;

        // Make an Axios GET request to the Laravel route
        const response = await axios.get('https://cookie-backend.test/read-cookies');

        // Update the cookies data with the received cookies
        this.cookies = response.data;
      } catch (error) {
        console.error('An error occurred while fetching cookies:', error.message);
      }
    }
  }
}
</script>
