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
      <input
        type="button"
        @click="changeBackground('purple')"
        value="purple"
        class="btn purple"
      />
      <input
        type="button"
        @click="changeBackground('green')"
        value="green"
        class="btn green"
      />
      <input
        type="button"
        @click="changeBackground('red')"
        value="red"
        class="btn red"
      />
      <input
        type="button"
        @click="changeBackground('blue')"
        value="blue"
        class="btn blue"
      />
      <input
        type="button"
        @click="changeBackground('yellow')"
        value="yellow"
        class="btn yellow"
      />
      <input
        type="button"
        @click="changeBackground('orange')"
        value="orange"
        class="btn orange"
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

.btn {
  padding: 10px 20px;
  cursor: pointer;
  border: none;
  color: #fff;
  border: 2px solid white;
  width: 100px;
  height: 100px;
  margin: 20px;
  border-radius: 100%;
  text-transform: capitalize;
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
