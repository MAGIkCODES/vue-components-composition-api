<script setup>
import { ref, onUnmounted} from 'vue' 
import CoffeePlan from '../components/CoffeePlan.vue'
const plans = ref(['The Single', 'The Curious', 'The Addict', 'The Hacker'])

const selectedCoffeePlan = ref()

const handleSelectPlan = (name) => {
    selectedCoffeePlan.value = name
}

const count = ref(0)
const interval = setInterval(() => {
    count.value++
    console.log('hello picker')
}, 1000)

onUnmounted(() => {
  clearInterval(interval)
  console.log('bye bye picker')
})


</script>

<template>
    <div  class="plans">
        {{ count }}
        <CoffeePlan 
            v-for="plan in plans" 
            :key="plan" 
            :name="plan"
            :selected="plan === selectedCoffeePlan"
            @selected="handleSelectPlan"
        >
        </CoffeePlan>
    </div>
</template>