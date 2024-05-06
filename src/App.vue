<script setup>
import HelloWorld from "./components/HelloWorld.vue";
</script>

<script>
import { ref } from "vue";

const greeting = "Selamat Datang di Halaman Tugas 2 ";
const name = ref("Your Name");
const isHighlighted = ref(false);

const updateName = (event) => {
  name.value = event.target.value;
  isHighlighted.value = true;
  setTimeout(() => {
    isHighlighted.value = false;
  }, 1000);
};
</script>

<template>
  <div>
    <h1>{{ greeting }}</h1>
    <p>
      Masukkan Nama Anda:
      <span :class="{ highlight: isHighlighted }">{{ name }}</span>
    </p>
    <input type="text" v-model="name" @input="updateName" />
  </div>
</template>

<style scoped>
.highlight {
  color: blue;
  font-weight: bold;
}

input[type="text"] {
  padding: 0.5em;
  margin-top: 0.5em;
  border: 1px solid #ccc;
  border-radius: 10px;
  width: 500px;
  height: 40px;
  background-color: rgba(255, 255, 255, 0.5);
}

input[type="text"]:focus {
  outline: none;
  border-color: #646cff;
  box-shadow: 0 0 5px #646cff;
  background-color: rgba(255, 255, 255, 0.5);
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
  background-color: rgba(255, 255, 255, 0.5);
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
