<script setup lang='ts'>
import { ref } from "vue"

/**
 * Implement a composable function that toggles the state
 * Make the function work correctly
*/
function useToggle(initial) {
  const value = ref(initial)

  const toggle = () => value.value = !value.value

  return [
    value,
    toggle,
  ]
}

const [state, toggle] = useToggle(false)

</script>

<template>
  <p>State: {{ state ? 'ON' : 'OFF' }}</p>
  <p @click="toggle">
    Toggle state
  </p>
</template>
