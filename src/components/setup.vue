<template>
  <button @click="increaseCount">count is: {{ state.count }}</button>
</template>

<script lang="ts" setup>
import { reactive } from 'vue'

const state = reactive({ count: 0 })

const increaseCount = () => {
  state.count++
}
</script>
