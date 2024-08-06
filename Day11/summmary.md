## 1.父子组件之间的props（属性）传递机制：
```js
在 Vue 中，props（属性）是父组件向子组件传递数据的一种机制。它们允许父组件将数据传递给子组件，从而使得组件之间能够共享和传递信息。

基本概念
定义：Props 是子组件的自定义属性，可以通过父组件传递数据到子组件。
子组件通过声明 props 来接收这些数据。

单向数据流：数据通过 props 从父组件流向子组件，子组件不应直接修改 props 的值，这有助于保持数据的单向流动和组件的独立性。如果需要修改，可以在子组件内部使用计算属性或数据副本。
```
## 2.使用 props:
- 1.在子组件中声明：
```js
<!-- ChildComp.vue -->
<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  msg: String
})
</script>

<template>
  <div>{{ props.msg }}</div>
</template>
```
- 2. 在父组件中传递 props
父组件通过在使用子组件时添加属性的方式传递数据。这些属性的名字必须与子组件中声明的 `props` ** 名字一致 **。
```js
<!-- Parent.vue -->
<template>
  <ChildComp msg="Hello from parent" />
</template>

<script setup>
import ChildComp from './ChildComp.vue'
</script>
```
## 3.可以在声明 props 时指定其类型，这样可以帮助开发者捕捉错误和提高代码可读性。例如，可以指定 props 是 String、Number、Boolean 等类型。还可以提供默认值和进行自定义的验证。
```js
<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  msg: {
    type: String,
    required: true, // 表示该 prop 是必须的
    default: 'Hello' // 默认值
  },
  count: {
    type: Number,
    default: 0
  }
})
</script>

<template>
  <div>
    <p>{{ props.msg }}</p>
    <p>{{ props.count }}</p>
  </div>
</template>
```
## 4.GPT link:https://chatgpt.com/share/883308d4-71fa-4882-8a4f-1862d5ef5c11