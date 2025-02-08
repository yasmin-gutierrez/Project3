<script setup>
import {ref} from 'vue';

</script>

<template>
  <main class="app">

    <div class="container">
      <h1>Countdown Timer</h1>
      <div class="content">
        <h3>Set Timer</h3>
        <form @submit.prevent="StartCountdown">
          <h4>Enter time (in seconds):</h4>
          <input type="number" v-model.number="timeInput" max="60" min="1" placeholder="Seconds" />
          <input type="submit" value="Start Countdown" />
        </form>
      </div>
    </div>

    

  </main>

</template>
