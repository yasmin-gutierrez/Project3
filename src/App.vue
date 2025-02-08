<script setup>
import {ref} from 'vue';

</script>

<template>
  <main class="app">

    <div class="container">
      <h1>Countdown Timer</h1>

      <div class="content">
        <label for="timeInput">Enter time (in seconds):</label>
        <input type="number" v-model="timeInput" max="60" min="1" placeholder="Seconds" />
      </div>

      <button @click="startCountdown" class="start-button">Start Countdown</button>

      <div class="timer">


      </div>
    </div>
  </main>
</template>
