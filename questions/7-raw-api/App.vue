<script setup lang="ts">
import { reactive, isReactive, toRaw, markRaw } from "vue"

const state = { count: 1 }
const reactiveState = reactive(state)

/**
 * Modify the code so that we can make the output be true.
*/
console.log(toRaw(reactiveState) === toRaw(state))

/**
 * Modify the code so that we can make the output be false.
*/
const info = markRaw({ count: 1 })
const reactiveInfo = reactive(info)

console.log(isReactive(reactiveInfo))

</script>

<template>
  <div>
    <p>
      {{ reactiveState.count }}
    </p>
  </div>
</template>
