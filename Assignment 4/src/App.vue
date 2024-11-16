<script setup>
import CosineLaw from "./components/CosineLaw.vue";
import AsymptoteFinder from "./components/AsymptoteFinder.vue";
import GregoryLeibnizPi from "./components/GregoryLeibnizPi.vue";
</script>

<template>
  <div class="calculator-container">
    <CosineLaw />
    <AsymptoteFinder />
    <GregoryLeibnizPi />
  </div>
</template>

<style scoped>
.calculator-container {
  font-family: Arial, Helvetica, sans-serif;
  background-color: rgb(238, 238, 238);
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  gap: 10vh;
  padding: 30px;
}
</style>
