<template>
  <Header>
    <h1>{{ title }}</h1>
    <button @click="Theme">Dark/White</button>
  </Header>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AppHeader',
  emits: ['theme-changed'],
  data() {
    return {
      DarkTheme: false,
    }
  },
  props: {
    title: {
      type: String,
      default: 'Header',
    },
  },
  methods: {
    Theme() {
      this.DarkTheme = !this.DarkTheme
      this.$emit('theme-changed', this.DarkTheme)
    },
  },
})
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
  gap: 25px;
}
button {
  padding: 5px 10px;
  border: none;
  background-color: aqua;
  border-radius: 5px;
  margin-right: 5px;
}
</style>
