<script setup>
import { ref } from "vue";

const emojis = ref([
  "😂",
  "😘",
  "😊",
  "🤣",
  "😍",
  "😁",
  "😢",
  "😎",
  "😉",
  "🙂",
  "🫡",
  "😮",
  "😥",
]);
const currentEmoji = ref(emojis.value[0]);

const getRandomEmoji = () => {
  const randomIndex = Math.floor(Math.random() * emojis.value.length);
  currentEmoji.value = emojis.value[randomIndex];
};
</script>

<template>
  <div class="flex w-full h-full justify-center items-center">
    <div
      @mouseover="getRandomEmoji"
      class="emoji big-box rounded-full mt-40 p-10 bg-slate-500"
    >
      <span>{{ currentEmoji }}</span>
    </div>
  </div>
</template>

<style scoped>
.big-box {
  width: 21%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.emoji {
  font-size: 10rem;
  filter: grayscale(1);
  cursor: pointer;
  transition-property: transform, filter;
  transition-duration: 200ms;
}

.emoji:hover {
  transform: scale(1.3);
  filter: grayscale(0);
}
</style>
