<script setup>
import {h, ref} from 'vue'

defineProps({
  //extra credit needs this

})
//define the messages this component may send to other components
const emit = defineEmits([
    'stats-entered' // we can pick the names
    //this message gets sent when the user
    //enters their data and app should do math
])
const height = ref('')
const weight = ref('')
function statsEntered(){
//   send the data to app.vue to do the math and display the data
  emit('stats-entered', height)
  emit('stats-entered', weight)
  //goes to this component's parent
  //where does this message go? App.vue
}

</script>

<template>
  <label>Height in meters</label>
  <input v-model="height">
  <label>Weight in Kilos</label>
  <input v-model="weight">
  <button v-on:click ="statsEntered">Calculate</button>

</template>

<style scoped>

</style>
