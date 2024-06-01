<script setup>
import { ref } from "vue";
import emoji from "./components/emoji.vue";

const showEmoji = ref(false);
</script>

<template>
  <div
    class="flex justify-center items-center h-10 bg-green-300 text-gray-700 py-5"
  >
    <button @click="showEmoji = !showEmoji">Emoji</button>
  </div>
  <div v-if="showEmoji">
    <emoji />
  </div>
</template>

<style scoped></style>
