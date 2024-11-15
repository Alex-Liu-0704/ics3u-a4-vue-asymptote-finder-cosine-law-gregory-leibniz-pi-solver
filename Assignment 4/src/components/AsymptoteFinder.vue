<script setup>
import { ref } from 'vue';

const m = ref(0);
const n = ref(0);
const asymptoteType = ref("");

function asymptoteFinder() {
    if (m.value === n.value) {
        asymptoteType.value = "The asymptote is horizontal";
    } else if (n.value > m.value) {
        asymptoteType.value = "The asymptote is the x-axis";
    } else {
        const differences = [
            "Linear", "Quadratic", "Cubic", "Quartic", "Quintic", "Sextic", "Septic", "Octic", "Nonic", "Decic"
        ]
        if ((m.value - n.value) <= 10) {
            asymptoteType.value = "The asymptote is " + differences[m.value - n.value - 1];
        } else {
            asymptoteType.value = "The asymptote out of range";
        }
    }
}
</script>

<template>
    <form @submit.prevent="asymptoteFinder()">
        <p>Asymptote Finder</p>
        <label>m Value:</label>
        <input type="number" v-model="m" /><br>
        <label>n Value:</label>
        <input type="number" v-model="n" /><br>
        <label>Asymptote Type (Result):</label>
        <input type="text" v-model="asymptoteType" readonly /><br>
        <button type="submit">Calculate</button>
    </form>
</template>

<style scoped>
</style>