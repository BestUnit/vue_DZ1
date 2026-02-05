<template>
  <div :class="[DarkTheme ? 'light-theme' : 'dark-theme']" class="root">
    <header class="header">
      <AppHeader @theme-changed="themeColor" />
    </header>
    <div class="Main_body">
      <section class="content">
        <h1 :style="{ color: isMainPageTitleGreen ? 'green' : 'black' }">Main Page</h1>
        <ClickCounter @decrement="decrementHandler" :title="$options.title" />
      </section>
      <section class="sidebar"><SideBar /></section>
    </div>
    <!-- <footer class="footer">Footer {{ 2 * 2 }} {{ new Date().getFullYear() }}</footer> -->
    <footer><AppFooter /></footer>
  </div>
</template>

<script lang="ts">
import AppFooter from '@/components/AppFooter.vue'
import AppHeader from '@/components/AppHeader.vue'
import ClickCounter from '@/components/ClickCounter.vue'
import SideBar from '@/components/SideBar.vue'

import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TestComponent',
  components: { ClickCounter, AppHeader, AppFooter, SideBar },

  data() {
    return {
      isMainPageTitleGreen: false,
      DarkTheme: true,
    }
  },
  title: 'Our counter title',
  computed: {
    root() {
      return {
        'dark-theme': this.DarkTheme,
        'light-theme': !this.DarkTheme,
      }
    },
  },
  methods: {
    decrementHandler(event: number) {
      this.isMainPageTitleGreen = event < -5 ? true : false
      console.log('decrement-handler', event)
    },
    themeColor() {
      this.DarkTheme = !this.DarkTheme
    },
  },
})
</script>

<style scoped>
.light-theme {
  background-color: #ffffff;
  color: #726464;
}
.dark-theme {
  background-color: #726464;
  color: #f0f0f0;
}
.root {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.header,
.footer {
  font-size: 32px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Main_body {
  display: flex;
  align-items: center;
  padding-inline: 50px;
}

.content,
.sidebar {
  flex-grow: 1;
  padding: 10px;
}
</style>
