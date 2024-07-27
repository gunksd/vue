// Vue 的核心功能是声明式渲染：通过扩展于标准 HTML 的模板语法，
//我们可以根据 JavaScript 的状态来描述 HTML 应该是什么样子的。当状态改变时, HTML 会自动更新。
//SFC
<script setup>
import { ref , reactive } from 'vue'
const counter = reactive({
    count:0
})
const message = ref('Hello Vue!')
const increment = () =>{
    counter.count++
}
console.log(counter.count) //print result is 0
console.log(message.value)
</script>

<template>
    <button @click="increment">
        <h1>
            {{ message }}
        </h1>
    </button>

    <p>
        Count is :{{ counter.count }}
    </p>
</template>