<script setup>
import ranking from "../components/ranking.vue";
import distance from "../components/distance.vue";
import courses from "../components/courses.vue";
import friendsRanking from "../components/friendsRanking.vue";
import { onMounted } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

onMounted(() => {
    AOS.init({
        duration: 800,
        once: true,
        offset: 100
    });
});
</script>

<template>
    <section class="home">
        <div class="container" data-aos="fade-up">
            <div class="welcome-section">
                <h1>Bienvenue sur BetterBeTrail</h1>
                <p class="subtitle">Votre compagnon de trail running</p>
            </div>
            <div class="stats-grid">
                <ranking />
                <distance />
                <courses />
            </div>  
            <div class="content-grid">
                <friendsRanking />
            </div>
        </div>
    </section>
</template>

<style scoped>
.home {
    min-height: 100vh;
    background: linear-gradient(135deg, #1a1c2e 0%, #2d3748 100%);
    padding: 2rem;
}

.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
}

.welcome-section {
    text-align: center;
    margin-bottom: 3rem;
}

h1 {
    font-size: 2.5rem;
    color: #ffffff;
    margin-bottom: 0.5rem;
    font-weight: 700;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.subtitle {
    font-size: 1.2rem;
    color: #a0aec0;
    font-weight: 500;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    align-items: center;
}

@media (max-width: 768px) {
    .home {
        padding: 1rem;
    }

    .container {
        padding: 1rem;
    }

    h1 {
        font-size: 2rem;
    }

    .subtitle {
        font-size: 1rem;
    }

    .stats-grid {
        grid-template-columns: 1fr;
        gap: 1.5rem;
    }
}
</style>
