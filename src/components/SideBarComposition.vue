<template>
  <div class="btn-group">
    <a href=""
      ><button>{{ SideBar }}</button></a
    >
    <a href=""
      ><button>{{ SideBar }}</button></a
    >
    <a href=""
      ><button>{{ SideBar }}</button></a
    >
    <a href=""
      ><button>{{ SideBar }}</button></a
    >
    <a href=""
      ><button>{{ SideBar }}</button></a
    >
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const SideBar = ref<string>('SideBar')
</script>

<style scoped>
button {
  border: 1px solid #1db8d3;
  border-radius: 5px;
  padding: 5px 10px;
  background-color: #1db8d3;
}

.btn-group {
  display: grid;
  gap: 25px;
  margin-right: 25px;
}
</style>
