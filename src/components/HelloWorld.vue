<template>
  <h1>{{ msg }}</h1>
  {{ mario }}
  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="counter++">counter is: {{ counter }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { ref, reactive } from 'vue'

const props = defineProps({
  msg: {
    type: String,
    default: ''
  },
  mario: {
    type: Number,
    default: 0
  }
})
let msg = reactive(props.msg)
let mario = reactive(props.mario)
msg = 'ciao'
mario = 22
const counter = ref(0)

// const state = reactive({ count: 0 })
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
