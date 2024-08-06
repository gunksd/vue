<script setup>
import { ref } from 'vue'
import ChildComp from './son.vue'

const greeting = ref('Hello from parent')
</script>

<template>
  <ChildComp :msg="greeting" />
</template>