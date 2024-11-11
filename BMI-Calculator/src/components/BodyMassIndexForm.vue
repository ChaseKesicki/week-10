<script setup>
import { ref } from 'vue'
// Show inputs for the user to enter their height in meters, and weight in kilograms.  Create two reactive data and use v-model to connect with the input elements. 
// Show a button with the text 'Calculate'
// When the user clicks the 'Calculate' button, BodyMassIndexForm should emit an event called stats-entered to App.vue with the user's height and the user's weight - this is the data the user entered in the inputs. 
// BodyMassIndexForm.vue will not receive any props from App.vue (but see extra credit question for an extra question about props)

defineProps({ //this program recieves no props from App.vue
})

const emit = defineEmits([  //sends back the raw stats, will be calculated in app.vue
  'stats-entered'
])

const weight = ref('')

const height = ref('')

function defineStats() {
  emit('stats-entered', { height: height.value, weight: weight.value})  //takes data from inputs and sends it to parent
}




</script>

<template>

  <h2>Enter your height and weight</h2>

  <div>
    <label for="height">Height in meters </label>
    <input v-model="height" id="height"><br>
    <label for="weight">Weight in kilograms </label>
    <input v-model="weight" id="weight">
  </div>
  <br>

  <button @click="defineStats">Calculate</button> 



</template>

<style scoped>
button{
  background-color: turquoise;
  border: 2px solid blue;
}
</style>
