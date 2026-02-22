<template>
  <div class="container" :class="theme">
    <AppHeaderComposition @theme-changed="ThemeChange" />
    <div class="main-body">
      <div class="container-body">
        <ClickCounterComposition
          @decrement="
            (event) => {
              console.log(event)
            }
          "
        />
        <SideBarComposition />
      </div>
    </div>
    <AppFooterComposition />
  </div>
</template>

<script setup lang="ts">
import AppFooterComposition from '@/components/AppFooterComposition.vue'
import AppHeaderComposition from '@/components/AppHeaderComposition.vue'
import ClickCounterComposition from '@/components/Composition/ClickCounterComposition.vue'
import SideBarComposition from '@/components/SideBarComposition.vue'
import { ref } from 'vue'

const theme = ref('light-theme')

const ThemeChange = (isDark: boolean) => {
  theme.value = isDark ? 'dark-theme' : 'light-theme'
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.main-body {
  flex-grow: 1;
}

.container-body {
  display: flex;
  justify-content: space-between;
}

.light-theme {
  background-color: #ffffff;
  color: #726464;
}
.dark-theme {
  background-color: grey;
  color: #ffffff;
}
</style>
