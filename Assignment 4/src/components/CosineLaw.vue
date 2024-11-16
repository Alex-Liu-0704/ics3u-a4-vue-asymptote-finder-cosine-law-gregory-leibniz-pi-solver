<script setup>
import { ref } from 'vue';

const a = ref(0);
const b = ref(0);
const angleC = ref(0);
const cResult = ref(0);

function cosineLaw() {
  if (angleC.value < 180 && a.value > 0 && b.value > 0) {
      const c = Math.sqrt(Math.pow(a.value, 2) + Math.pow(b.value, 2) - (2 * a.value * b.value * Math.cos(angleC.value * (Math.PI / 180))));
      cResult.value = c.toFixed(5);
  }
}
</script>

<template>
  <form @submit.prevent="cosineLaw()">
    <p>Cosine Law</p>
    <label>Side a:</label>
    <input type="number" v-model="a" /><br />
    <label>Side b:</label>
    <input type="number" v-model="b" /><br />
    <label>Angle C:</label>
    <input type="number" v-model="angleC" /><br />
    <label>Side c (Result):</label>
    <input v-model="cResult" type="number" readonly /><br />
    <button type="submit">Calculate</button>
  </form>
</template>

<style scoped>
form {
  background-color: rgb(255, 255, 255);
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 70px;
  width: 40vw;
  min-height: 650px;
  max-height: 700px;
  min-width: 350px;
  height: 100vh;
  text-align: center;
  border-radius: 25px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

p {
  font-size: 30px;
  font-weight: bold;
  max-width: 300px;
  padding-bottom: 15px;
}

label {
  font-size: 20px;
  font-weight: bold;
  padding-top: 10px;
  display: inline-block;
  text-align: left;
  width: 25vw;
}

input, button{
  width: 25vw;
  min-width: 200px;
  height: 7vh;
  max-height: 40px;
  margin-top: 10px;
  border-radius: 5px;
  border: 2px solid rgba(200, 200, 200, 0.5);
  padding: 5px;
  font-size: 20px;
}

input[readonly] {
  background-color: rgba(128, 128, 128, 0.329);
  text-align: left;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

button {
  border: 2px solid rgba(200, 200, 200, 0);
  background-color: rgb(0, 140, 255);
  color: white;
}

button:hover {
  background-color: rgb(0, 89, 255);
}
</style>