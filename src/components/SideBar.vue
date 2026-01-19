<template>
  <div>
    {{ title }}
    <p>что-то</p>
    <p>что-то</p>
    <p>что-то</p>
    <p>что-то</p>
    <p>что-то</p>
    <p>что-то</p>
    <p>что-то</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    title: {
      type: String,
      default: 'Sidebar',
    },
  },
})
</script>

<style scoped></style>
