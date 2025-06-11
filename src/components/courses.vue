<script setup>
import { ref } from 'vue'


const completedCourses = ref(0)
</script>

<template>
    <div class="courses">
        <div class="stats-container">
            <div class="stat-card">
                <div class="stat-icon">🏃</div>
                <div class="stat-content">
                    <h3>Courses Complétées</h3>
                    <p class="stat-number">{{ completedCourses }}</p>
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
    transition: transform 0.2s ease;
}

.stat-card:hover {
    transform: translateY(-2px);
}

.stat-icon {
    font-size: 2.5rem;
    margin-right: 20px;
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

@media (max-width: 768px) {
    .stats-container {
        grid-template-columns: 1fr;
    }
}
</style>
