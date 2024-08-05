<template>
    <button :class="type">{{ label }}</button>
  </template>
  
  <script>
  export default {
    props: {
      label: String,
      type: String
    }
  }
  </script>
  