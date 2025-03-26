<script setup>
import { ref } from 'vue';
const status = ref(null);

fetch('/api/status')
    .then(response => response = response.json())
    .then(data => status.value = data);
</script>

<template>
    <div class="main">
      <h2>Status:</h2>
      <h3 v-if="status">{{status.status}}</h3>
      <h3 v-else="status">Not running</h3>
    </div>
</template>

<style scoped>
  .main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: Arial, sans-serif;
    background-color: aliceblue;
  }
</style>
