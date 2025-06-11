<script setup>
import Navbar from "./components/Navbar.vue";
</script>

<template>
    <div class="app-background">
        <Navbar />
        <router-view />
    </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap");

/* Palette "primary" personnalisée */
:root {
    --primary-600: #2563eb;
    --primary-400: #60a5fa;
    --background-main: #334155;
}

html,
body {
    height: 100%;
    margin: 0;
    padding: 0;
    background: var(--background-main);
    font-family: "Montserrat", Arial, Helvetica, sans-serif;
}
.app-background {
    min-height: 100vh;
    font-family: "Montserrat", Arial, Helvetica, sans-serif;
}
</style>
