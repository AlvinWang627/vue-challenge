<script setup lang="ts">
import { ref, Ref, reactive, isRef, unref, toRef, toRefs } from 'vue'

const initial = ref(10)
const count = ref(0)

// Challenge 1: Update ref
function update(value) {
  count.value = value
}

/**
 * Challenge 2: Checks if `count` is a ref object.
 * Make the output to be 1
 */
console.log(
  // impl ? 1 : 0
  isRef(count) ?? 1
)

/**
 * Challenge 3: Unwrap ref
 * Make the output to be true
 */
function initialCount(value: number | Ref<number>) {
  count.value = unref(value)
  // Make the output to be true
  console.log(unref(value) === 10)
}

initialCount(initial)

/**
 * Challenge 4:
 * create a ref for a property on a source reactive object.
 * The created ref is synced with its source property:
 * mutating the source property will update the ref, and vice-versa.
 * Make the output to be true
 */
const state = reactive({
  foo: 1,
  bar: 2
})
const fooRef = toRefs(state) // change the impl...
const test = ref(state)

console.log(test)
console.log(fooRef)
// mutating the ref updates the original
fooRef.foo.value++
console.log(state.foo === 2)

// mutating the original also updates the ref
state.foo++
console.log(fooRef.foo.value === 3)
</script>

<template>
  <div>
    <h1>msg</h1>
    <p>
      <span @click="update(count - 1)">-</span>
      {{ count }}
      <span @click="update(count + 1)">+</span>
    </p>
  </div>
</template>
