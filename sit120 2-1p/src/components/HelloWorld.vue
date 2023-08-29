<script setup>
import { ref } from 'vue'

const triggered = ref(false)
</script>

<template>
  <div class="greetings">
    <h1 v-if="triggered">The button has been pressed...</h1>
    <button @click="triggered = !triggered" v-if="triggered">Hide</button>
    <button @click="triggered = !triggered" v-else>Show</button>
  </div>
</template>
