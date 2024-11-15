<script setup>
import { ref } from 'vue';

const n = ref(0);
const piApprox = ref(0);

function piApproximation() {
    let pi = 0;
    for (let i = 0; i < n.value; i++) {
        pi += ((-1) ** i) / (2 * i + 1);
    }
    piApprox.value = (pi * 4);
}
</script>

<template>
    <form @submit.prevent="piApproximation()">
        <p>Gregory–Leibniz Pi Approximation</p>
        <label>n Value:</label>
        <input type="number" v-model="n"><br>
        <label>Pi Approximation (Result):</label>
        <input v-model="piApprox" type="number" readonly /><br>
        <button type="submit">Calculate</button>
    </form>
</template>

<style scoped>
</style>