<script setup>
import { ref , onMounted} from "vue";
import emoji from "./components/emoji.vue";
import InterchangeableColors from "./components/InterchangeableColors.vue";
import feedBack from "./components/feedBack.vue";
import calculator from "./components/calculator.vue";
import { gsap } from "gsap";



const Emoji = ref(false);
const Color = ref(false);
const FeedBack = ref(false);
const Calculator = ref(false);


const textColor = ref("");

const showEmoji = () => {
  Emoji.value = !Emoji.value;
  Color.value = false;
  FeedBack.value = false;
  Calculator.value = false;
};

const showColor = () => {
  Color.value = !Color.value;
  Emoji.value = false;
  FeedBack.value = false;
  Calculator.value = false;
};

const showFeedBack = () => {
  FeedBack.value = !FeedBack.value;
  Emoji.value = false;
  Color.value = false;
  Calculator.value = false;
};
const showCalculator = () => {
  Calculator.value = !Calculator.value;
  Emoji.value = false;
  Color.value = false;
  FeedBack.value = false;
};

const handleColorChange = (color) => {
  textColor.value = color;
};



onMounted(() => {
  gsap.to(".box", {
    x: 100,
    duration: 2,
  });
});
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
    <button :style='[`color: ${textColor} ;`]' @click="showCalculator">
      calculator
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
  <div v-else-if="Calculator">
    <calculator />
  </div>
  <div
    v-else
    class="flex text-white py-5 text-[50px] justify-center items-center h-[400px] box"
  >
    Please choose something from the navBar!
    </div>
    <div class="bg-yellow-500 w-[50px] h-[50px] rounded-full box">
    </div>
</template>

<style scoped>
.btn {
  padding: 2px 20px;

}
</style>
