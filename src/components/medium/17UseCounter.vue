<script setup lang="ts">
interface UseCounterOptions {
  min?: number
  max?: number
}
import { ref } from 'vue'
/**
 * Implement the composable function
 * 1. inc (+)
 * 2. dec (-)
 * 3. reset
 * 4. min & max opotion support
 * Make sure the function works correctly
 */
function useCounter(initialValue = 0, options: UseCounterOptions = {}) {
  const { min, max } = options
  const count = ref(initialValue)
  const inc = () => {
    if (max === undefined || count.value < max) {
      count.value++
    }
  }
  const dec = () => {
    if (min === undefined || count.value > min) {
      count.value--
    }
  }
  const reset = () => {
    count.value = initialValue
  }

  return {
    count,
    inc,
    dec,
    reset
  }
}

const { count, inc, dec, reset } = useCounter(0, { min: 0, max: 10 })
</script>
<template>
  <div>{{ count }}</div>
  <div @click="inc">++</div>
  <div @click="dec">--</div>
  <div @click="reset">reset</div>
</template>
