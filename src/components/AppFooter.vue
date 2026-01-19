<template>
  <footer>{{ title }}</footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    title: {
      type: String,
      default: 'Footer',
    },
  },
})
</script>

<style scoped>
footer {
  display: flex;
  justify-content: center;
  font-size: 32px;
}
</style>
