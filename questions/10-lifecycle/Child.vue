<script setup lang="ts">
import { onMounted, inject, onUnmounted } from "vue"

const timer = inject("timer")
const count = inject("count")

onMounted(() => {
  timer.value = window.setInterval(() => {
    count.value++
  }, 1000)
})

onUnmounted(() => {
  clearInterval(timer.value)
})
</script>

<template>
  <div>
    <p>
      Child Component: {{ count }}
    </p>
  </div>
</template>
