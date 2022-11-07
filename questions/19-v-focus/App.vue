<script setup lang='ts'>
import { ref } from "vue"

const state = ref(false)

/**
 * Implement the custom directive
 * Make sure the input element focuses/blurs when the 'state' is toggled
 *
*/

const VFocus = {
  mounted(el: HTMLElement, binding: any) {
    binding.value && el.focus()
  },
  updated(el: HTMLElement, binding: any) {
    binding.value ? el.focus() : el.blur()
  },
}

setInterval(() => {
  state.value = !state.value
}, 2000)

</script>

<template>
  <input v-focus="state" type="text">
</template>
