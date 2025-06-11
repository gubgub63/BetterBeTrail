<script setup>
const position = 1; // Remplace par une prop ou donnée dynamique si besoin
const placesGained = 12; // Remplace par une prop ou donnée dynamique si besoin
</script>

<template>
    <div class="stat-card">
        <div class="stat-icon">
            <div class="ranking-number">#{{ position }}</div>
        </div>
        <div class="stat-content">
            <h3>Classement</h3>
            <div class="ranking-info">
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
    transition: transform 0.2s ease;
}

.stat-card:hover {
    transform: translateY(-2px);
}

.stat-icon {
    font-size: 2.5rem;
    margin-right: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
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
