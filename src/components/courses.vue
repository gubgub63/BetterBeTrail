<script setup>
import { ref, onMounted } from 'vue'

const completedCourses = ref(0)
const isLoading = ref(true)

onMounted(() => {
    // Simuler un chargement pour démontrer l'animation
    setTimeout(() => {
        completedCourses.value = 12
        isLoading.value = false
    }, 1500)
})
</script>

<template>
    <div class="courses">
        <div class="stats-container">
            <div class="stat-card" :class="{ 'is-loading': isLoading }">
                <div class="stat-icon">🏃</div>
                <div class="stat-content">
                    <h3>Courses Complétées</h3>
                    <div class="stat-value-container">
                        <p class="stat-number" v-if="!isLoading">{{ completedCourses }}</p>
                        <div class="skeleton-loader" v-else></div>
                    </div>
                </div>
                <div class="tooltip">
                    <span class="tooltip-icon">ℹ️</span>
                    <span class="tooltip-text">Nombre total de courses que vous avez terminées</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.courses {
    padding: 20px;
}

.stats-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.stat-card {
    background: linear-gradient(135deg, #6366f1 0%, #4f46e5 100%);
    border-radius: 12px;
    padding: 20px;
    color: white;
    display: flex;
    align-items: center;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
    position: relative;
}

.stat-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.stat-icon {
    font-size: 2.5rem;
    margin-right: 20px;
    transition: transform 0.3s ease;
}

.stat-card:hover .stat-icon {
    transform: scale(1.1);
}

.stat-content h3 {
    margin: 0;
    font-size: 1rem;
    font-weight: 500;
    opacity: 0.9;
}

.stat-number {
    margin: 5px 0 0 0;
    font-size: 2rem;
    font-weight: bold;
}

/* Tooltip styles */
.tooltip {
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: help;
}

.tooltip-icon {
    font-size: 1rem;
    opacity: 0.7;
    transition: opacity 0.3s ease;
}

.tooltip:hover .tooltip-icon {
    opacity: 1;
}

.tooltip-text {
    visibility: hidden;
    position: absolute;
    top: 100%;
    right: 0;
    background: rgba(0, 0, 0, 0.8);
    color: white;
    padding: 8px 12px;
    border-radius: 6px;
    font-size: 0.875rem;
    width: 200px;
    z-index: 1;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.tooltip:hover .tooltip-text {
    visibility: visible;
    opacity: 1;
}

/* Skeleton loader */
.skeleton-loader {
    width: 60px;
    height: 2rem;
    background: linear-gradient(
        90deg,
        rgba(255, 255, 255, 0.1) 25%,
        rgba(255, 255, 255, 0.2) 50%,
        rgba(255, 255, 255, 0.1) 75%
    );
    background-size: 200% 100%;
    animation: loading 1.5s infinite;
    border-radius: 4px;
}

@keyframes loading {
    0% {
        background-position: 200% 0;
    }
    100% {
        background-position: -200% 0;
    }
}

@media (max-width: 768px) {
    .stats-container {
        grid-template-columns: 1fr;
    }
}
</style>
