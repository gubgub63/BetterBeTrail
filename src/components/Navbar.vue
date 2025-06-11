<template>
    <div class="navclass">
        <nav class="navbar">
            <router-link class="title" to="/" exact>TrailApp</router-link>
            <router-link to="/trails">Courses</router-link>
            <router-link to="/map">Classement</router-link>
            <router-link to="/favorites">Communautés</router-link>
        </nav>
        <p>Profile</p>
    </div>
</template>

<script setup>
import router from "@/router";
</script>

<style scoped>
.navclass {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 1rem;
    margin-right: 10%;
    align-items: center;
}

.navbar {
    display: flex;
    gap: 2rem;
    padding: 1rem;
    flex-direction: row;
    justify-content: left;
    margin-left: 10%;
    align-items: center;
}

.title {
    font-size: 1.5rem; /* correspond à text-2xl */
    font-weight: bold;
    color: var(--primary-600);
}

.router-link-active {
    color: #42b983;
}
a {
    color: white;
    text-decoration: none;
    transition:
        color 0.3s,
        transform 0.3s cubic-bezier(0.4, 2, 0.6, 1);
}
a:hover {
    color: var(--primary-400);
    transform: translateY(-3px) scale(1.07);
}
</style>
