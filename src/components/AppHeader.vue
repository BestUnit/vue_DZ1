<template>
  <header >
    <h1>{{ title }}</h1>
    <button @click="toggleTheme">Dark/White</button>
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
    toggleTheme() {
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
  border: 5px solid #111;
  background-color: rgb(74, 80, 138);
  border-radius: 5px;
}

</style>
