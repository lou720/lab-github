<script setup>
import { ref } from 'vue'

const t = "Laboratorio fra pari"
const text = ref(t)
const text_color = ref('black')

function laboratoriofraparipp() {
  text.value = text.value + randomemoji() + ' ' + t 
  text_color.value = randomcolor()
}

function randomcolor() {
	const randomColor = Math.floor(Math.random() * 0xffffff).toString(16);
	return "#" + randomColor;
}

function randomemoji() {
  const emojis = [
    '😀', '😃', '😄', '😁', '😆', '😅', '🤣', '😂',
    '🙂', '🙃', '😉', '😊', '😇', '🥰', '😍', '🤩',
    '😘', '😗', '😚', '😙', '🥲', '😋', '😛', '😜',
    '🤪', '😌', '😔', '😑', '😐', '😶', '🤫', '🤭',
    '🤫', '🤐', '🤨', '😐', '😏', '😒', '🙁', '☹️',
    '😲', '😞', '😖', '😢', '😭', '😤', '😠', '😡',
    '🤬', '😈', '👿', '💀', '☠️', '💩', '🤡', '👹',
    '👺', '👻', '👽', '👾', '🤖', '😺', '😸', '😹',
    '😻', '😼', '😽', '🙀', '😿', '😾', '❤️', '🧡',
    '💛', '💚', '💙', '💜', '🖤', '🤍', '🤎', '💔'
  ];
  
  return emojis[Math.floor(Math.random() * emojis.length)];
}
</script>

<template>
  <div class="container">
    <h1 :style="{ color: text_color }">{{ text }}</h1>
    <button @click="laboratoriofraparipp">Ancora!</button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  gap: 2rem;
}

h1 {
  font-size: 2.5rem;
  font-weight: bold;
  text-align: center;
  transition: color 0.3s ease;
  margin: 0;
}

button {
  padding: 1.5rem 3rem;
  font-size: 1.5rem;
  font-weight: bold;
  color: white;
  background-color: #e74c3c;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

button:hover {
  background-color: #c0392b;
  transform: scale(1.05);
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
}

button:active {
  transform: scale(0.98);
}
</style>