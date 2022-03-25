<template>
  <h1>{{ secondes }}</h1>
  <h1>{{ totalIdleTime }}</h1>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const secondes = ref(0);
const totalIdleTime = ref(0);

setInterval(() => {
  secondes.value++;
  totalIdleTime.value += secondes.value;
}, 1000);

function mouseMove(event: MouseEvent) {
  secondes.value = 0;
}

onMounted(() => window.addEventListener('mousemove', mouseMove));
onUnmounted(() => window.removeEventListener('mousemove', mouseMove));
</script>

<style lang="scss">
@import './assets/scss/base.scss';
</style>
