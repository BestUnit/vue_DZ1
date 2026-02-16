<template>
    <div class="container" :class="theme"  >
        <AppHeader @theme-changed="ThemeChange"/>
            <div class="main-body">
                <ClickCounterComposition @decrement="(event) => {console.log(event)}"/>
            </div>
        <AppFooter />
    </div>
</template>

<script setup lang="ts">
import AppFooter from '@/components/AppFooter.vue';
import AppHeader from '@/components/AppHeader.vue';
import ClickCounterComposition from '@/components/Composition/ClickCounterComposition.vue';
import { ref } from 'vue';

const theme = ref('light-theme')

const ThemeChange = (isDark: boolean) => {
  theme.value = isDark ? 'dark-theme' : 'light-theme';
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

.light-theme {
  background-color: #ffffff;
  color: #726464;
}
.dark-theme {
  background-color: grey;
  color: #ffffff;
}
</style>