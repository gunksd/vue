<script setup>
import { ref } from 'vue'
//定义一个变量，初始为零，可以增加，有三种乃至更多状态
const state = ref( 0 )

function toggle() {
    state.value = (state.value + 1) % 3
}
</script>

<template>
  <button @click="toggle">Toggle</button>
  <h1 v-if="state === 0">Vue is awesome!</h1>
  <h1 v-else-if="state === 1">Hello Vue</h1>
  <h1 v-else>Oh no 😢</h1>
</template>