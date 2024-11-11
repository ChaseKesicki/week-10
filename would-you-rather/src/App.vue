<script setup>
import WouldYouRather from './components/WouldYouRather.vue' //Links child element

import { ref } from 'vue'

const  wyrQuestion = ref('Live in a house shaped like a triangle or a house shaped like a circle?')
const wyrAnswer1 = ref('Triangle house')
const wyrAnswer2 = ref('Circle house')

// this will store the user's answer once they make a choice

const userSelection = ref('')

function updateUserSelection(userChoice){
  userSelection.value = `Thanks! You chose ${userChoice}`
}
</script>

<template>

  <div id="app-components">

    <h1>Would You Rather</h1>
    
    <!--V-bind sends data to the WYR child, v-on recieves data from WYR child-->
    <WouldYouRather 
    v-bind:question="wyrQuestion" 
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-selected="updateUserSelection" 
    ></WouldYouRather>

    <p>{{ userSelection }}</p>

</div>

</template>



<style scoped>
p {
  font-family:'Courier New', Courier, monospace;
}

#app-components{
  /*font-size: 3em;*/
  background-color: aqua;
  padding: 40px;
}

</style>
