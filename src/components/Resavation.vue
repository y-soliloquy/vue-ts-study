<script setup lang="ts">
import UITitle from './ui/UITitle.vue';</script>

<template>
    <div class="container">
        <UITitle>スロット</UITitle>
        <div class="card">
            <span>Badges</span>
            <div class="badges">
                <span>VIP</span>
                <span>NORMAL</span>
            </div>
        </div>

        <div class="resavation-card">
            <span>John Wick1</span>
            <div class="badges">
                <span>VIP</span>
            </div>
        </div>

        <div class="resavation-card">
            <span>John Wick2</span>
            <div class="badges">
                <span>NORMAL</span>
            </div>
        </div>

        <div class="resavation-card">
            <span>John Wick3</span>
            <div class="badges">
                <span>NORMAL</span>
            </div>
        </div>
    </div>
</template>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.card {
    width: 300px;
    height: 80px;
    background-color: #ccc;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 24px;
    border-radius: 8px;
    box-shadow: 4px 4px 4px rgb(211, 211, 211)
}

.resavation-card {
    width: 400px;
    height: 60px;
    background-color: rgb(255, 212, 147);
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
    border-radius: 8px;
    box-shadow: 4px 4px 4px rgb(211, 211, 211)
}
</style>
