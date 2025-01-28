<script setup lang="ts">
import { ref } from "vue";

// Props (tipo stringa)
defineProps<{ msg: string }>();

// Stato reattivo
const messages = ref<string[]>([]);
const newMessage = ref("");

// Funzione per aggiungere un nuovo messaggio
function addMessage() {
  if (newMessage.value.trim() !== "") {
    messages.value.push(newMessage.value);
    newMessage.value = "";
  }
}
</script>

<template>
  <div>
    <!-- Mostriamo la prop ricevuta -->
    <h1>{{ msg }}</h1>

    <!-- Input con two-way binding -->
    <input v-model="newMessage" type="text" placeholder="Write a message..." />

    <!-- Pulsante per aggiungere il messaggio -->
    <button @click="addMessage">send</button>

    <!-- Lista dei messaggi -->
    <ul>
      <li v-for="(message, index) in messages" :key="index">
        {{ message }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
h1 {
  color: #42b983;
}

input {
  margin-right: 0.5em;
  padding: 0.5em;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 0.5em 1em;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #36a174;
}

ul {
  margin-top: 1em;
  list-style: none;
  padding: 0;
}

li {
  padding: 0.5em 0;
  border-bottom: 1px solid #eee;
}
</style>
