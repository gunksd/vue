<script setup>
import { ref } from 'vue'
const increment = () => {
  count.value++
}
const count = ref(0)
</script>

<template>
    <h1 class="counter">
  <button class="counter" @click="increment">
    Count is: {{ count }}
  </button>
    </h1>
</template>

<style>
.counter{
   color: rgb(255, 106, 0);
   background-color: rgb(64, 55, 55); /* 设置按钮背景颜色 */
   border: none; /*移除默认边框*/
   padding: 5px 5px;/*增加内边距*/
   border-radius: 5px;/*圆角边框*/
   display: flex;/*将按钮变成弹性容器？*/
   align-items: center; /* 垂直居中 */
   justify-content: center; /* 水平居中 */
   width: 150px; /* 根据需要设置宽度 */
   height: 50px; /* 根据需要设置高度 */
}
</style>