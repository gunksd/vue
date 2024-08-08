<template>
  <div class="card">
    <div class="card-header">
      <slot name="header">Default Header</slot>
    </div>
    <div class="card-body">
      <slot>Default Body</slot>
    </div>
    <div class="card-footer">
      <slot name="footer">Default Footer</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card'
}
</script>

<style>
.card {
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 16px;
  margin: 16px;
}
.card-header {
  font-weight: bold;
  margin-bottom: 8px;
}
.card-body {
  margin-bottom: 8px;
}
.card-footer {
  font-size: 0.9em;
  color: #777;
}
</style>
