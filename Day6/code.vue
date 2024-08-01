<script setup>
import { ref } from 'vue'

// 给每个 todo 对象一个唯一的 id
let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn JavaScript' },
  { id: id++, text: 'Learn Vue' }
])

function addTodo() {
  newTodo.value = newTodo.value.trim() //去掉输入值两端的空白字符，以避免空格对输入内容的影响。
  if (newTodo.value.length === 0) {
    return
  }
  todos.value.push({ id: id++, text: newTodo.value })
  newTodo.value = ''   //reset
}

function removeTodo(todo) {
  todos.value = todos.value.filter(t => t !== todo) 
  //filter 遍历所有事项，判断是否等于当前你要删除的事项，
  //如果的确不相等，那么会返回true，就可以加入新的列表中，
  //如果与你要删除的那个事项相同，那就返回false，就不会被添加到新的列表里，
  //其中相当于一个双重否定的意思
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="new todo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>