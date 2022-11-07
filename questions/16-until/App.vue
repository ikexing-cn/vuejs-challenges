<script setup lang='ts'>
import { ref, watch } from "vue"

const count = ref(0)

/**
 * Implement the until function
*/

function until(initial) {
  async function toBe(value) {
    return new Promise<void>((resolve) => {
      const unWatch = watch(initial, (val) => {
        if (val === value) {
          unWatch()
          resolve()
        }
      })
    })
  }

  return {
    toBe,
  }
}

async function increase() {
  count.value = 0
  setInterval(() => {
    count.value++
  }, 1000)
  await until(count).toBe(3)
  console.log(count.value === 3) // Make sure the output is true
}

</script>

<template>
  <p @click="increase">
    Increase
  </p>
</template>
