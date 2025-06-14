<script setup>
import { ref } from 'vue';

const friends = ref([
    {
        name: 'John Doe',
        position: 1,
        kilometers: 100
    },
    {
        name: 'Enzo',
        position: 2,
        kilometers: 90,
        me :true
    },
    {
        name: 'Lucie',
        position: 3,
        kilometers: 80
    },
    {
        name: 'John Doe',
        position: 3,
        kilometers: 80
    }
])

</script>
<template>
    <div class="friends-ranking">
        <h1>Classement des amis</h1>
        <div class="friends-list">
            <div class="header">
                <div>Nom</div>
                <div>Kilomètres</div>
                <div>Position</div>
            </div>
            <div
                class="friend-item"
                v-for="friend in friends"
                :key="friend.name + friend.position"
                :class="{ top1: friend.position === 1, top2: friend.position === 2, top3: friend.position === 3 }"
            >
                <div class="friend-name">
                    <span v-if="friend.position === 1" class="badge gold">
                        <svg width="18" height="18" viewBox="0 0 20 20" fill="none">
                            <circle cx="10" cy="10" r="8" fill="#FFD700" stroke="#FFD700" stroke-width="2"/>
                            <text x="10" y="14" text-anchor="middle" font-size="10" font-weight="bold" fill="#fff">1</text>
                        </svg>
                    </span>
                    <span v-else-if="friend.position === 2" class="badge silver">
                        <svg width="18" height="18" viewBox="0 0 20 20" fill="none">
                            <circle cx="10" cy="10" r="8" fill="#C0C0C0" stroke="#C0C0C0" stroke-width="2"/>
                            <text x="10" y="14" text-anchor="middle" font-size="10" font-weight="bold" fill="#fff">2</text>
                        </svg>
                    </span>
                    <span v-else-if="friend.position === 3" class="badge bronze">
                        <svg width="18" height="18" viewBox="0 0 20 20" fill="none">
                            <circle cx="10" cy="10" r="8" fill="#cd7f32" stroke="#cd7f32" stroke-width="2"/>
                            <text x="10" y="14" text-anchor="middle" font-size="10" font-weight="bold" fill="#fff">3</text>
                        </svg>
                    </span>
                    <span v-if="friend.me" class="me">
                        <svg viewBox="0 0 20 20" fill="currentColor" width="18" height="18" style="vertical-align: middle;">
                            <circle cx="10" cy="6.5" r="3.5"/>
                            <path d="M2 17c0-2.5 3-4.5 8-4.5s8 2 8 4.5V18H2v-1z"/>
                        </svg>
                    </span>
                    <span>{{ friend.name }}</span>
                </div>
                <p>{{ friend.kilometers }} km</p>
                <p class="friend-pos">{{ friend.position }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.friends-ranking {
    background: linear-gradient(135deg, #23243a 0%, #2d3748 100%);
    padding: 32px 24px;
    border-radius: 18px;
    color: #fff;
    font-family: 'Montserrat', 'Inter', 'Segoe UI', Arial, sans-serif;
    box-shadow: 0 4px 24px 0 rgba(30, 67, 138, 0.10);
    max-width: 500px;
    margin: 0 auto;
}

.friends-ranking h1 {
    font-size: 1.7rem;
    font-weight: 800;
    margin-bottom: 1.5rem;
    letter-spacing: 1px;
    text-align: center;
}

.friends-list {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.header, .friend-item {
    display: grid;
    grid-template-columns: 2.5fr 1.2fr 1fr;
    align-items: center;
    justify-content: space-between;
    padding: 0.7rem 1.2rem;
    border-radius: 10px;
}

.header {
    background: rgba(99, 102, 241, 0.10);
    font-size: 1.1rem;
    font-weight: 700;
    color: #a0aec0;
    margin-bottom: 0.5rem;
}

.friend-item {
    background: rgba(255,255,255,0.04);
    margin-bottom: 0.2rem;
    font-size: 1.08rem;
    font-weight: 600;
    color: #e2e8f0;
    transition: background 0.2s, transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 2px 8px 0 rgba(99, 102, 241, 0.04);
}
.friend-item:hover {
    background: linear-gradient(90deg, #6366f1 0%, #60a5fa 100%);
    color: #fff;
    transform: translateY(-2px) scale(1.02);
    box-shadow: 0 4px 16px 0 rgba(99, 102, 241, 0.10);
}

.friend-name {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    min-width: 0;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.badge {
    font-size: 1.2rem;
    margin-right: 0.2rem;
}
.gold {
    filter: drop-shadow(0 0 4px #ffd700cc);
}
.silver {
    filter: drop-shadow(0 0 4px #c0c0c0cc);
}
.bronze {
    filter: drop-shadow(0 0 4px #cd7f32cc);
}

.friend-pos {
    font-weight: 700;
    font-size: 1.1rem;
    color: #60a5fa;
}

@media (max-width: 600px) {
    .friends-ranking {
        padding: 16px 4px;
        max-width: 100%;
    }
    .header, .friend-item {
        font-size: 0.98rem;
        padding: 0.5rem 0.5rem;
        grid-template-columns: 1.5fr 1fr 0.8fr;
    }
}
.me {
    font-size: 1.2rem;
    margin-right: 0.2rem;
    color: #60a5fa;
    display: inline-flex;
    align-items: center;
    vertical-align: middle;
}
</style>