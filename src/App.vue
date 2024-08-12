<script setup>
import { ref} from 'vue'
// import CoffeePlan from './components/CoffeePlan.vue'
import PlanPicker from './components/PlanPicker.vue'
import FancyButton from './components/FancyButton.vue'

const show = ref(true)



</script>


<template>
<div class="content">
  <!-- <PlanPicker/> -->
  <h1 class="title">Coffee Plans</h1>

  <h2 class="subtitle">We travel the world to source the very best single origin coffee for you</h2>

  <label ><input type="checkbox" v-model="show">Show plan picker</label>
  <PlanPicker v-if="show"/>

  <FancyButton>
    <!-- //scoped slot -->
    <template #icon{hover}>
      {{ hover ? '👋' : '👊' }}
    </template>
    Submit
  </FancyButton>
</div>
    
  
</template>