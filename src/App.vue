<template>
  <h1>{{ secondes }}</h1>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnMounted } from 'vue';

const secondes = ref(0);

setInterval(() => {
  secondes.value++;
}, 1000);

function mouseMove(event: MouseEvent) {
  secondes.value = 0;
}

onMounted(() => window.addEventListener('mousemove', mouseMove));
onUnMounted(() => window.removeEventListener('mousemove', mouseMove));
</script>

<style lang="scss">
@import './assets/scss/base.scss';
</style>
