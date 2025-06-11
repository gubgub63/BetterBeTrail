<template>
    <div class="nav-container">
        <nav class="navbar">
            <router-link class="title" to="/" exact>
                <svg class="logo" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                </svg>
                <span>TrailApp</span>
            </router-link>
            <div class="nav-links">
                <router-link to="/trails" class="nav-link">
                    <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                    </svg>
                    <span>Courses</span>
                </router-link>
                <router-link to="/map" class="nav-link">
                    <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                    </svg>
                    <span>Classement</span>
                </router-link>
                <router-link to="/favorites" class="nav-link">
                    <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
                        <circle cx="9" cy="7" r="4"/>
                        <path d="M23 21v-2a4 4 0 0 0-3-3.87"/>
                        <path d="M16 3.13a4 4 0 0 1 0 7.75"/>
                    </svg>
                    <span>Communautés</span>
                </router-link>
            </div>
        </nav>
        <div class="profile-section">
            <button class="profile-button">
                <svg class="profile-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                    <circle cx="12" cy="7" r="4"/>
                </svg>
                <span>Profile</span>
            </button>
        </div>
    </div>
</template>

<script setup>
import router from "@/router";
</script>

<style scoped>
.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: rgba(26, 28, 46, 0.95);
    backdrop-filter: blur(10px);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.navbar {
    display: flex;
    align-items: center;
    gap: 3rem;
}

.title {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 1.5rem;
    font-weight: 700;
    color: white;
    text-decoration: none;
    transition: all 0.3s ease;
    background: none !important;
}

.title:hover {
    transform: translateY(-2px);
    color: #6366f1;
    background: none !important;
    box-shadow: none !important;
}

.logo {
    width: 24px;
    height: 24px;
    stroke: currentColor;
}

.nav-links {
    display: flex;
    gap: 2rem;
    align-items: center;
}

.nav-link {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    color: #a0aec0;
    text-decoration: none;
    font-weight: 500;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    transition: all 0.3s ease;
}

.nav-link:hover {
    color: white;
    background: rgba(255, 255, 255, 0.1);
    transform: translateY(-2px);
}

.router-link-active {
    color: white;
    background: rgba(255, 255, 255, 0.1);
}

.icon {
    width: 20px;
    height: 20px;
    stroke: currentColor;
}

.profile-section {
    display: flex;
    align-items: center;
}

.profile-button {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.1);
    color: white;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
}

.profile-button:hover {
    background: rgba(255, 255, 255, 0.2);
    transform: translateY(-2px);
}

.profile-icon {
    width: 20px;
    height: 20px;
    stroke: currentColor;
}

@media (max-width: 768px) {
    .nav-container {
        padding: 1rem;
    }

    .navbar {
        gap: 1.5rem;
    }

    .nav-links {
        gap: 1rem;
    }

    .nav-link span:not(.icon) {
        display: none;
    }

    .profile-button span:not(.profile-icon) {
        display: none;
    }
}
</style>

