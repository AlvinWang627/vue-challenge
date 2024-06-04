<script setup>
import { nextTick, ref } from 'vue'

const count = ref(0)

async function increment() {
  count.value++
  await nextTick()
  // nextTick(() => {
  //   console.log(+document.getElementById('counter').textContent === 1)
  // })
  /**
   * DOM is not yet updated, how can we make sure that the DOM gets updated
   * Make the output be true
   */
  console.log(+document.getElementById('counter').textContent)
  console.log(+document.getElementById('counter').textContent === 1)
}
</script>

<template>
  <button id="counter" @click="increment">
    {{ count }}
  </button>
</template>
