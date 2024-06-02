<script setup>
import { ref, watch } from "vue";

const background = ref("");
// Watcher to log changes to background value
watch(background, (newValue) => {
  console.log("background", newValue);
  document.body.style.backgroundColor = newValue;
  emit("colorChange", newValue);
});

// Method to change the background color
const changeBackground = (color) => {
  background.value = color;
};

const emit = defineEmits(["colorChange"]);
</script>

<template>
  <div class="content-container">
    <nav class="nav">
      <img
        src="../assets/img/plum.png"
        @click="changeBackground('purple')"
        class="w-[150px] cursor-pointer"
        alt=""
      />

      <img
        src="../assets/img/apple.png"
        @click="changeBackground('green')"
        class="w-[150px] cursor-pointer"
        alt=""
      />

      <img
        src="../assets/img/cherry.png"
        @click="changeBackground('red')"
        class="w-[150px] cursor-pointer"
        alt=""
      />

      <img
        src="../assets/img/blueberry.png"
        @click="changeBackground('blue')"
        class="w-[150px] cursor-pointer"
        alt=""
      />

      <img
        src="../assets/img/banana.png"
        @click="changeBackground('yellow')"
        class="w-[150px] cursor-pointer"
        alt=""
      />

      <img
        src="../assets/img/orange.png"
        @click="changeBackground('orange')"
        class="w-[150px] cursor-pointer"
        alt=""
      />
    </nav>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: rgb(28, 28, 35);
}

.nav {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
}

.purple {
  background-color: purple;
}

.green {
  background-color: green;
}

.red {
  background-color: red;
}

.blue {
  background-color: blue;
}

.yellow {
  background-color: yellow;
}

.orange {
  background-color: orange;
}

.content-container {
  height: 70vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
