<script setup lang="ts">
import { ref, computed, watch, watchEffect } from 'vue'

/**
 * Implement the composable function
 Make sure the function works correctly
*/
//computed
// function useLocalStorage(key: string, initialValue: any) {
//   const value = ref(initialValue)
//   localStorage.setItem(key, JSON.stringify(value.value))
//   const counter = computed({
//     get() {
//       value.value = JSON.parse(localStorage.getItem(key))
//       return value.value
//     },
//     set(newValue: number) {
//       value.value = newValue
//       localStorage.setItem(key, JSON.stringify(value.value))
//     }
//   })

//   return counter
// }

//watch
function useLocalStorage(key: string, initialValue: any) {
  const value = ref(JSON.parse(localStorage.getItem(key)) ?? initialValue)
  // watch(
  //   value,
  //   () => {
  //     localStorage.setItem(key, JSON.stringify(value.value))
  //   },
  //   { immediate: true, deep: true }
  // )
  watchEffect(() => {
    localStorage.setItem(key, JSON.stringify(value.value))
  })
  return value
}

const counter = useLocalStorage('counter', 0)

// We can get the localStorage by triggering the getter:

console.log(counter.value)

// And we also can set the localStorage by triggering the setter:

// counter.value = 1
console.log(counter.value)
const plusOne = () => {
  counter.value++
}
</script>
<template>
  <div>{{ counter }}</div>
  <div @click="plusOne">+1</div>
</template>
