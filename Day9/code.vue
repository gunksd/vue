<script setup>
import { ref, watch } from 'vue'

const todoId = ref(1)
const todoData = ref(null)
const isFetching = ref(false)

async function fetchData() {
  if (isFetching.value) return
  isFetching.value = true
  todoData.value = null

  try {
    const res = await fetch(`https://jsonplaceholder.typicode.com/todos/${todoId.value}`)
    if (!res.ok) throw new Error('Failed to fetch data')
    todoData.value = await res.json()
  } catch (error) {
    console.error(error)
    todoData.value = { error: error.message }
  } finally {
    isFetching.value = false
  }
}

fetchData()
watch(todoId, fetchData)
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button @click="todoId++" :disabled="isFetching">Fetch next todo</button>
  <p v-if="isFetching">Loading...</p>
  <pre v-else-if="todoData && todoData.error">{{ todoData.error }}</pre>
  <pre v-else>{{ todoData }}</pre>
</template>
