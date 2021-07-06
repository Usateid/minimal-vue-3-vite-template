// RFC for events //
https://github.com/vuejs/rfcs/blob/master/active-rfcs/0030-emits-option.md
<template>
  <div>
    <p>Click here to send an emit</p>
    <button
      type="button"
      @click="emit('submit', { email: 'a', password: '2' })"
    >
      emit
    </button>
  </div>
</template>

<script setup>
import { defineEmit } from 'vue'

const emit = defineEmit({
  submit: (payload) => {
    if (payload.email && payload.password) {
      return true
    } else {
      console.warn(`Invalid submit event payload!`)
      return false
    }
  }
})
</script>
