<script setup>
import { ref,onMounted } from 'vue'
onMounted(() => {
  pElementRef.value.textContent = 'message.value'
})
const pElementRef = ref(null)
</script>

<template>
  <p ref="pElementRef">Hello</p>
</template>