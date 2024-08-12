<script setup>
const props = defineProps({
  name:{ 
    type: String, 
    default: 'Default Plan', 
    //props validation
    validator(value){
    return value.startsWith("The");
  }},
  selected: { type: Boolean, default: false},
  
})

const emit = defineEmits({
  //emits validation
  selected(payload){
    return typeof payload === 'string'
  }
})

const selectePlan = () => {
  emit('selected', props.name)
}
</script>

<template>
  <div @click="selectePlan" :class="{'active-plan': selected}" class="plan">
      <div class="description">
        <span class="title"> {{ name }} </span>
      </div>
    </div>
</template>