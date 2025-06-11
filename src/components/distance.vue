<script setup>
import { ref } from "vue";

const distance = ref(127);
</script>

<template>
    <div class="stat-card">
        <div class="stat-icon">
            <svg width="32" height="32" fill="none" viewBox="0 0 24 24">
                <circle
                    cx="12"
                    cy="12"
                    r="10"
                    fill="white"
                />
                <path
                    d="M8 16l4-8 4 8"
                    stroke="#4f46e5"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                />
            </svg>
        </div>
        <div class="stat-content">
            <h3>Distance Totale</h3>
            <p class="stat-number">{{ distance }} km</p>
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

.stat-number {
    margin: 5px 0 0 0;
    font-size: 2rem;
    font-weight: bold;
}
</style>
