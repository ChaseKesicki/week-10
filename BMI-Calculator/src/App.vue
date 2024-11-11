<script setup>
import { ref } from 'vue'
import BodyMassIndexForm from './components/BodyMassIndexForm.vue'
// Display the app's name, 'Body Mass Index Calculator'
// Receive the stats-entered event from BodyMassIndexForm, and use the data sent to calculate the user's body mass index
// To calculate the body mass index, assuming variables called height and weight,  const bmi = weight / ( height * height )
// Display the calculated body mass index, formatted to 2 decimal places. 
// App.vue will not pass any props to BodyMassIndexForm (but see next credit question for an extra question about props) 
const userBMI = ref('')

function calculateBMI({height, weight}) {  //code to validate data and calculate BMI
  if (height && weight) {  
  const bmi = weight / (height * height)
  userBMI.value = bmi.toFixed(2)
  }
}


</script>

<template>

  <h1>Body Mass Index Calculator</h1>
  <!--Recieves weight and height, and uses it in function to calculate BMI-->
  <BodyMassIndexForm
  v-on:stats-entered="calculateBMI"  
  ></BodyMassIndexForm>

  <p>BMI is: {{ userBMI }}</p>  <!--BMI is displayed here-->
</template>

<style scoped>
</style>
