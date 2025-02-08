<script setup>
import {ref} from 'vue';

const timeInput = ref("");
const timeLeft = ref(null);
const countdown = ref(null);

const startCountdown = () => {
  const time = parseInt(timeInput.value, 10);
  if (!isNaN(time) && time >= 1 && time <= 60) {
    timeLeft.value = time;
    clearInterval(countdown.value);
    countdown.value = setInterval(() => {
      if (timeLeft.value > 0) {
        timeLeft.value--;
      } else {
        clearInterval(countdown.value);
        alert('Time is up!');
        timeLeft.value = null;
      }
    }, 1000);
  } else {
    alert('Please enter a valid number between 1 and 60.');
  }
};

</script>

<template>
  <main class="app">

    <div class="container">
      <h1>Countdown Timer</h1>

      <div class="content">
        <label for="timeInput">Enter Time (In Seconds):</label>
        <input type="number" v-model="timeInput" max="60" min="1" placeholder="Seconds" />
      </div>

      <button @click="startCountdown" class="start-button">Start Countdown</button>

      <div class="timer" v-if="timeLeft !== null">
        {{ timeLeft }} seconds
      </div>

    </div>
  </main>
</template>
