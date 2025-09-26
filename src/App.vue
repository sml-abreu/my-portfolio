<script setup lang="ts">
import NavBar from './components/NavBar.vue';
</script>

<template>
    <div class="app">
        <router-view />
        <NavBar />
    </div>
</template>

<style scoped>
.app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}
</style>
