<template>
    <button @mouseover="hover = true" @mouseleave="hover = false">
        <slot name="icon" :hover="hover" random="hello justice"></slot><slot></slot>
    </button >
    {{ hover }}
</template>

<script setup>
import { ref }  from 'vue'

const hover = ref(false)
</script>

<style scoped>
button {
  display: inline-block;
  color: #fff;
  background-color: #09848d;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  border-radius: 0.25rem;
  text-transform: uppercase;
  font-weight: 500;
  font-size: 0.875rem;
  border-width: 2px;
  border-color: #09848d;
  letter-spacing: 0.2;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
</style>