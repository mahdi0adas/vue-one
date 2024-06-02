<script setup></script>

<template>
  <div class="big-box">
    <section class="panel-container" id="panel">
      <strong>Your Feedback 👀</strong>
      <div class="ratings-container">
        <div class="container">
          <div class="rating">
            <div class="icon">😒</div>
            <small>Unhappy</small>
          </div>
          <div class="rating">
            <div class="icon">😐</div>
            <small>Neutral</small>
          </div>
          <div class="rating">
            <div class="icon">😊</div>
            <small>Satisfied</small>
          </div>
        </div>
      </div>
      <button class="btn" id="send">Send Feedback</button>
    </section>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.big-box {
  /* background: rgb(26, 25, 25); */
  font-family: sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

.panel-container {
  background: #1d1c1c;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.3);
  border-radius: 4px;
  font-size: 90%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 30px;
  width: 700px;
  color: #fff;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 500px;
}

.panel-container strong {
  line-height: 20px;
  text-align: center;
}

.ratings-contaienr {
  display: flex;
  margin: 20px 0;
}

.rating {
  flex: 1;
  cursor: pointer;
  padding: 20px;
  margin: 10px 5px;
}

.rating:hover,
.rating.active {
  border-radius: 4px;
  background: #ccc;
  transition: 1s ease;
}

.rating .icon {
  width: 40px;
  font-size: 5rem;
  margin-right: 10px;
}

.rating small {
  color: #fff;
  display: inline-block;
  margin: 10px 0 0;
}

.btn {
  background: #fff;
  color: #000;
  border: 0;
  border-radius: 4px;
  padding: 12px 30px;
  cursor: pointer;
  outline: 0;
}

.btn:active {
  transform: scale(0.98);
}

.heart {
  font-size: 3rem;
  margin-bottom: 10px;
}
</style>
