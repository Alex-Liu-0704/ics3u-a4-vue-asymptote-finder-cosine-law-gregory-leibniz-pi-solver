<script setup>
import { ref } from 'vue';

const a = ref(0);
const b = ref(0);
const angleC = ref(0);
const c = ref(0);
const cResult = ref(0);

function cosineLaw() {
    if (angleC.value < 180 && a.value > 0 && b.value > 0) {
        c.value = Math.sqrt((a.value ** 2) + (b.value ** 2) - (2 * a.value * b.value * Math.cos(angleC.value * (Math.PI / 180))));
        cResult.value = c.value.toFixed(5);
    }
}
</script>

<template>
    <form @submit.prevent="cosineLaw()">
        <p>Cosine Law</p>
        <label>Side a:</label>
        <input type="number" v-model="a" /><br>
        <label>Side b:</label>
        <input type="number" v-model="b" /><br>
        <label>Angle C:</label>
        <input type="number" v-model="angleC" /><br>
        <label>Side c (Result):</label>
        <input v-model="cResult" type="number" readonly /><br>
        <button type="submit">Calculate</button>
    </form>
</template>

<style scoped>
</style>