<script setup>
import { ref, watch } from "vue";

const numberOne = ref("");
const numberTwo = ref("");
const selectOp = ref("");
const theResults = ref("");

watch(
  [numberOne, numberTwo, selectOp],
  ([newValueOne, newValueTwo, newValuEThree]) => {
    console.log(newValueOne);
    console.log(newValueTwo);
    console.log(newValuEThree);
  }
);

const submitBtn = () => {
  if (selectOp.value === "plus") {
    theResults.value = numberOne.value + numberTwo.value;
  } else if (selectOp.value === "min") {
    theResults.value = numberOne.value - numberTwo.value;
  } else if (selectOp.value === "dev") {
    theResults.value = numberOne.value / numberTwo.value;
  } else {
    theResults.value = numberOne.value * numberTwo.value;
  }
};
</script>

<template>
  <div class="main">
    <div class="inputs">
      <h1 v-if="theResults" class="result text-center my-4">
        {{ theResults }}
      </h1>
      <h1 v-else class="result text-center my-4">Result</h1>
      <select v-model="selectOp" id="selectOp">
        <option value="plus">+</option>
        <option value="min">-</option>
        <option value="dev">/</option>
        <option value="multi">*</option>
      </select>
      <input
        class="num1"
        type="number"
        placeholder="Number 1"
        v-model="numberOne"
      />
      <input
        class="num2"
        type="number"
        placeholder="Number 2"
        v-model="numberTwo"
      />
    </div>
    <div class="submitBtn">
      <button @click="submitBtn" id="btn">Submit</button>
    </div>
  </div>
</template>

<style scoped>
.main {
  display: flex;
  padding: 5px 0;
  position: absolute;
  left: 35%;
  width: 30%;
  background: gray;
  border-radius: 20px;
  flex-direction: column;
  margin-top: 73px;
  align-items: center;
}

.inputs {
  display: flex;
  flex-direction: column;
  width: 90%;
}

.inputs input {
  border: none;
  border-radius: 5px;
  width: 100%;
  outline: none;
  margin-bottom: 10px;
}

#selectOp {
  margin-bottom: 10px;
  padding: 10px;
  outline: none;
}

#btn {
  border: none;
  background: transparent;
  color: white;
  padding: 10px 20px;
  border: 2px solid white;
  margin-top: 10px;
  cursor: pointer;
}
</style>
