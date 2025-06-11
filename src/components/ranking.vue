<script setup>
import { ref, onMounted } from 'vue'

const position = ref(0)
const placesGained = ref(0)
const isLoading = ref(true)

onMounted(() => {
    // Simuler un chargement pour démontrer l'animation
    setTimeout(() => {
        position.value = 1
        placesGained.value = 12
        isLoading.value = false
    }, 1500)
})
</script>

<template>
    <div class="stat-card" :class="{ 'is-loading': isLoading }">
        <div class="stat-icon">
            <div class="ranking-number">#{{ position }}</div>
        </div>
        <div class="stat-content">
            <h3>Classement</h3>
            <div class="stat-value-container">
                <div v-if="!isLoading" class="ranking-info">
                    <p class="stat-number">{{ position }}</p>
                    <div
                        class="ranking-move"
                        :class="{ up: placesGained > 0, down: placesGained < 0 }"
                    >
                        <span v-if="placesGained > 0">▲ {{ placesGained }}</span>
                        <span v-else-if="placesGained < 0">▼ {{ Math.abs(placesGained) }}</span>
                        <span v-else>–</span>
                    </div>
                </div>
                <div v-else class="skeleton-loader"></div>
            </div>
        </div>
        <div class="tooltip">
            <span class="tooltip-icon">ℹ️</span>
            <span class="tooltip-text">Votre position dans le classement général et votre progression</span>
        </div>
    </div>
</template>

<style scoped>
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
    display: flex;
    align-items: center;
    justify-content: center;
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

.ranking-info {
    display: flex;
    align-items: center;
    gap: 10px;
}

.stat-number {
    margin: 5px 0 0 0;
    font-size: 2rem;
    font-weight: bold;
}

.ranking-move {
    font-size: 1.2rem;
    font-weight: 600;
    display: flex;
    align-items: center;
    transition: color 0.3s;
}

.ranking-move.up {
    color: #22c55e;
    animation: upMove 0.5s;
}

.ranking-move.down {
    color: #ef4444;
    animation: downMove 0.5s;
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
    width: 100px;
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

@keyframes upMove {
    0% {
        transform: translateY(8px);
        opacity: 0.5;
    }
    100% {
        transform: translateY(0);
        opacity: 1;
    }
}

@keyframes downMove {
    0% {
        transform: translateY(-8px);
        opacity: 0.5;
    }
    100% {
        transform: translateY(0);
        opacity: 1;
    }
}
</style>
