<template>
  <h2>Computed and Watcher</h2>
  <p>The value counter is: {{ counter }}</p>
  <button type="button" @click="counter++">Increase counter</button>
  <p>The computed is the counter * 2: {{ counterComputed }}</p>
  <p>For the watcher open the console</p>
  <a
    href="https://v3.vuejs.org/guide/reactivity-computed-watchers.html#computed-values"
    target="_blank"
    >Computed Values</a
  >
</template>

<script setup>
import { ref, computed, watch } from 'vue'

const counter = ref(1)

const counterComputed = computed(() => counter.value * 2)

watch(() => console.log('watch counter:', counter.value))
</script>

<style lang="scss" scoped></style>
