<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <hello-world msg="Hello Vue 3 + Vite" />
  <hr />
  <props-reactivity
    :counter="22"
    :user="{ firstName: 'Mario', lastName: 'Rossi' }"
    :list="['Ananas', 'Bluberry', 'Carrot', 'Dolphin']"
  />
  <hr />
  <computed-watcher />
</template>

<script setup>
import { HelloWorld, PropsReactivity, ComputedWatcher } from '@/components'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/script-setup-2/active-rfcs/0000-script-setup.md
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
