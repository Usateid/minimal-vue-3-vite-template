<template>
  <h1>Working with prop</h1>
  <div class="container">
    <div class="border-right padding-50">
      <h3>Increase the value of the prop counter</h3>
      <button type="button" @click="counter++">Increase</button>
      <p>counter is: {{ counter }}</p>
    </div>
    <div class="border-right padding-50">
      <h3>Change the user Object prop</h3>
      <input type="text" v-model="user.firstName" />
      <input type="text" v-model="user.lastName" />
      <p>Fullname: {{ user.firstName }} {{ user.lastName }}</p>
    </div>
    <div class="padding-50">
      <h2>Update a list</h2>
      <button type="button" @click="addUser">Add User</button>
      <button type="button" @click="list.pop">Remove Last element</button>
      <p>
        {{ list }}
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

const props = defineProps({
  counter: {
    type: Number,
    default: 0
  },
  user: {
    type: Object,
    default: () => ({})
  },
  list: {
    type: Array,
    default: () => []
  }
})

// Create a reactive reference of the prop Counter, so we can use it
// numberOfClicks is now an object => { value: counter }
const counter = ref(props.counter)
console.log('Counter is not an object with value:', counter.value)

// For Object we use the reactive method because ref is for primitive
const user = reactive(props.user)

const list = reactive(props.list)

const addUser = () => {
  list.push(user.firstName + ' ' + user.lastName)
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
}

.border-right {
  border-right: 1px solid black;
}
.padding-50 {
  padding: 0px 50px 0px 50px;
}
</style>
