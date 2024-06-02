<script setup>
import { ref } from "vue";
import emoji from "./components/emoji.vue";
import InterchangeableColors from "./components/InterchangeableColors.vue";
import feedBack from "./components/feedBack.vue";



const Emoji = ref(false);
const Color = ref(false);
const FeedBack = ref(false);
const textColor = ref("");

const showEmoji = () => {
  Emoji.value = !Emoji.value;
  Color.value = false;
  FeedBack.value = false;
};

const showColor = () => {
  Color.value = !Color.value;
  Emoji.value = false;
  FeedBack.value = false;
};

const showFeedBack = () => {
  FeedBack.value = !FeedBack.value;
  Emoji.value = false;
  Color.value = false;
};

const handleColorChange = (color) => {
  textColor.value = color;
};
</script>

<template>
  <div
    class="flex gap-3 justify-center items-center h-[30px] bg-black text-white py-5"
  >
    <button 
    :style='[`color: ${textColor} ;`]' @click="showEmoji">
      Emoji
    </button>
    <button :style='[`color: ${textColor} ;`]' @click="showColor">
      Color
    </button>
    <button :style='[`color: ${textColor} ;`]' @click="showFeedBack">
      Feed Back
    </button>
  </div>
  <div v-if="Emoji">
    <emoji />
  </div>
  <div v-else-if="Color">
    <InterchangeableColors   @colorChange="handleColorChange" />
  </div>
  <div v-else-if="FeedBack">
    <feedBack />
  </div>
  <div
    v-else
    class="flex text-white py-5 text-[50px] justify-center items-center h-[400px]"
  >
    Please choose something from the navBar!
  </div>
</template>

<style scoped>
.btn {
  padding: 2px 20px;

}
</style>
