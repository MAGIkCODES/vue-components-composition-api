<script setup>
import { ref } from 'vue' 
import CoffeePlan from '../components/CoffeePlan.vue'
const plans = ref(['The Single', 'The Curious', 'The Addict', 'The Hacker'])

const selectedCoffeePlan = ref()

const handleSelectPlan = (name) => {
    selectedCoffeePlan.value = name
}

</script>

<template>
    <div class="plans">
        {{ selectedCoffeePlan }}
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