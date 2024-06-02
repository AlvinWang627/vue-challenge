<script setup>
//1. 方法一，用內置指令去新增v-model的修飾符，貌似vue不建議，可能導致維護性問題
// import { ref, vModelText } from 'vue'
// const toUpperCase = (el, val) => {
//   const value = val.value
//   if (value.length === 0) {
//     return
//   } else {
//     el.value = value[0].toUpperCase() + value.substring(1)
//   }
// }
// vModelText.beforeUpdate = (el, val) => {
//   toUpperCase(el, val)
// }
// vModelText.mounted = (el, val) => {
//   toUpperCase(el, val)
// }
// const capitalize = ref('bbb')

// 2. 方法二寫 custom directives   v-capitalizeDirective
// import { onUpdated, ref } from 'vue'
// const capitalize = ref('abc')
// const vCapitalizeDirective = {
//   mounted(el) {
//     el.value = capitalize.value[0].toUpperCase() + capitalize.value.slice(1)
//   },
//   updated(el) {
//     el.value = capitalize.value[0].toUpperCase() + capitalize.value.slice(1)
//   }
// }

// 3. 方法三 computed
import { ref, computed } from 'vue'

const val = ref('')
const capitalizedValue = computed({
  get() {
    return val.value.trim().charAt(0).toUpperCase() + val.value.trim().slice(1)
  },
  set(newValue) {
    val.value = newValue
  }
})
</script>

<template>
  <input type="text" v-model="capitalizedValue" />
</template>
