<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import HeroAboutSection from './components/HeroAboutSection.vue';
import AboutMe from './components/AboutMe.vue';
import Experience from './components/Experience.vue';
</script>

<template>
    <div class="app">
        <NavBar />
        <HeroAboutSection />
        <AboutMe />
        <Experience />
    </div>
</template>

<style scoped>
.app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    position: relative;
}
</style>
