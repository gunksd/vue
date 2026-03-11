<script setup>
import {ref} from "vue"

const isActive = ref(false)
const counter = ref(0)
const Title = ref("title")
const message = ref('RED')
const counterClass = ref('counter')

const increment = () => {
      counter.value++
}

const toggle = () => {
  isActive.value = !isActive.value
}
</script>

<template>

  <button @click="increment">
    <h1 :class="Title">
      {{ message }}
    </h1>
  </button>

  <button @click="toggle(),increment()"> 
    <!--工程化做法是封装成一个函数：
      const handleclick = () =>{
            toggle()
            increment()
      } 
    然后绑定直接@click="handleclick"
    -->
    <h2 :class=" {active: isActive} ">
      {{ Title }}
    </h2>
  </button>

  <p :class="counterClass">

  计数是：{{ counter }}

  </p>
</template>

<style>
.title {
  color: red;
}

.counter {
  color: blue;
}

.active {
  color: blueviolet;
}
</style>
