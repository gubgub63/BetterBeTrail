<template>
    <nav class="navbar">
        <p>TrailApp</p>
        <router-link to="/" exact>Home</router-link>
        <router-link to="/trails">Trails</router-link>
        <router-link to="/map">Map</router-link>
        <router-link to="/favorites">Favorites</router-link>
        <router-link to="/profile">Profile</router-link>
    </nav>
</template>

<script setup></script>

<style scoped>
.navbar {
    display: flex;
    gap: 2rem;
    padding: 1rem;
    flex-direction: row;
    justify-content: left;
    margin-left: 10%;
    align-items: center;
    p {
        font-size: 1.5rem; /* correspond à text-2xl */
        font-weight: bold;
        color: var(--primary-600);
    }
}

.router-link-active {
    color: #42b983;
}
a {
    color: gray;
    text-decoration: none;
}
</style>
