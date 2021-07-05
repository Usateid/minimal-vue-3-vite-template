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
import { ref, computed, watch, watchEffect } from 'vue'

const counter = ref(1)
const hiddenValue = ref(0)

const counterComputed = computed(() => counter.value * 2)

watch(counter, () => console.log('watch counter:', counter.value))

watchEffect(() => {
  console.log('Counter or hiddenValue have changed')
  console.log('-hiddenValue updates every 5 seconds-')
  console.log('counter:', counter.value)
  console.log('hiddenValue:', hiddenValue.value)
})

setTimeout(() => {
  hiddenValue.value++
  // -> logs 1
}, 5000)
</script>

<style lang="scss" scoped></style>
