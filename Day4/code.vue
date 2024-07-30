<script setup>
import { ref } from 'vue'

const count = ref(0)
const text = ref('')

const increment = () => {
  count.value++
}

</script>

<template>
    <div class="container">
        <h1>Vue counter</h1>
        <div class="controls">
            <button @click="increment">
                Count is: {{ count }}
            </button>
            <input v-model="text" placeholder="Type here">
        </div>
        <p class="counter">{{ text }}</p>
    </div>
</template>

<style>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: top 20px; 
}

.controls {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
}

button {
    color: rgb(14, 87, 36);
    background-color: rgb(45, 145, 233);
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: rgb(190, 164, 164);
}

input {
    padding: 5px;
    border-radius: 5px;
    border: 1px solid rgb(55, 60, 187);
}

.output {
    color: rgb(42, 160, 117);
    margin-top: 20px;
    font-size: 18px;
}
</style>