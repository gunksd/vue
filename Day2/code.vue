<script setup>
import { ref,reactive } from "vue";
const titleclass = ref('title')
const Count=ref('count')
const counter = reactive({
    count:0
})
const message = ref ('Make me red!')
const increment = () =>{
    counter.count++
}
</script>

<template>
<button @click="increment">
  <h1 :class="titleclass">
    {{ message }}
  </h1>
</button>
<p :class="Count">
    Count is :{{ counter.count }}
</p>
</template>

<style>
.title {
  color: red;
}
.count {
    color: blue;
}
</style>
