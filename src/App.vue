<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import HeroSection from './components/HeroSection.vue';
import AboutMe from './components/AboutMe.vue';
import Experience from './components/Experience.vue';
import BackToTop from './components/BackToTop.vue';
</script>

<template>
    <div class="app">
        <NavBar />
        <HeroSection />
        <AboutMe />
        <Experience />
        <BackToTop />
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
