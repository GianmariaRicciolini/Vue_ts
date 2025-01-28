<script setup lang="ts">
import HelloWorld from "./components/HelloWorld.vue";
import { ref } from "vue"; // Importiamo ref per creare una reattività

// Variabile reattiva
const counter = ref(0);

// Funzione per incrementare il contatore
function increment() {
  counter.value++;
}
</script>

<template>
  <div>
    <h1>Here the first change!</h1>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <p>You clicked the button {{ counter }} times.</p>
    <button @click="increment">Click here</button>
  </div>
  <!-- Manteniamo HelloWorld per mostrare l'uso dei componenti -->
  <HelloWorld msg="Learning Vue!" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
button {
  margin-top: 1em;
  padding: 0.5em 1em;
  font-size: 1rem;
  background-color: #42b883;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 300ms;
}
button:hover {
  background-color: #36a174;
}
</style>
