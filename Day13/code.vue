<script setup>
import { ref } from 'vue'
import Card from './Card.vue'
const msg = ref('from parent')
</script>

<template>
    <div>
      <Card>
        <template #header>
          <h3>Custom Header</h3>
        </template>
        <template #default>
          <p>This is some custom body content.</p>
          <p>More details in the body section.</p>
        </template>
        <template #footer>
          <p>Custom Footer</p>
        </template>
      </Card>
    </div>
</template>
  

  