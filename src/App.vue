<script setup>
import { ref } from "vue";
import emoji from "./components/emoji.vue";
import InterchangeableColors from "./components/InterchangeableColors.vue";

const Emoji = ref(false);
const Color = ref(false);
const textColor = ref("");

const showEmoji = () => {
  Emoji.value = !Emoji.value;
  Color.value = false;
};

const showColor = () => {
  Color.value = !Color.value;
  Emoji.value = false;
};

const handleColorChange = (color) => {
  textColor.value = color;
};
</script>

<template>
  <div
    class="flex gap-3 justify-center items-center h-[30px] bg-[#9bff9b] text-white py-5"
  >
    <button :class="[`btn text-[${textColor}]`]" @click="showEmoji">
      Emoji
    </button>
    <button :class="[`btn text-[${textColor}]`]" @click="showColor">
      Color
    </button>
  </div>
  <div v-if="Emoji">
    <emoji />
  </div>
  <div v-else-if="Color">
    <InterchangeableColors @colorChange="handleColorChange" />
  </div>
  <div
    v-else
    class="flex text-red-500 text-[50px] justify-center items-center h-[400px]"
  >
    Please choose something from the navBar!
  </div>
</template>

<style scoped>
.btn {
  padding: 2px 20px;
}
</style>
