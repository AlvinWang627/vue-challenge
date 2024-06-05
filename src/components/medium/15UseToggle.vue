<script setup lang="ts">
import { Ref, ref } from 'vue'
/**
 * Implement a composable function that toggles the state
 * Make the function work correctly
 */
function useToggle(defaultState: boolean = false): [state: Ref, toggle: () => void] {
  const state = ref(defaultState)
  const toggle = () => {
    state.value = !state.value
  }
  return [state, toggle]
}

const [state, toggle] = useToggle(false)
</script>

<template>
  <p>State: {{ state ? 'ON' : 'OFF' }}</p>
  <p @click="toggle">Toggle state</p>
</template>
