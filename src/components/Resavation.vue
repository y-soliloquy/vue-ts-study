<script setup lang="ts">
import { ref } from 'vue';
import UITitle from './ui/UITitle.vue';
import Card from './Card.vue';
import Badge from './Badge.vue';

const isListVisible = ref<boolean>(true);

const onClickButton = () => {
    isListVisible.value = !isListVisible.value
}
</script>

<template>
    <div class="container">
        <UITitle>スロット</UITitle>
        <Card class="menu-card">
            <span style="font-weight: bold; font-size: 25px;">Badges</span>
            <div class="badges">
                <Badge class="vip-badge">
                    <span>VIP</span>
                </Badge>
                <Badge class="normal-badge">
                    <span>NORMAL</span>
                </Badge>
            </div>
        </Card>
        <div v-if="isListVisible">
            <Card class="resavation-card">
                <span>John Wick1</span>
                <Badge class="vip-badge">
                    <span>VIP</span>
                </Badge>
            </Card>
            <Card class="resavation-card">
                <span>John Wick2</span>
                <Badge class="normal-badge">
                    <span>NORMAL</span>
                </Badge>
            </Card>
            <Card class="resavation-card">
                <span>John Wick3</span>
                <Badge class="normal-badge">
                    <span>NORMAL</span>
                </Badge>
            </Card>
        </div>


        <button @click="onClickButton">Change</button>
    </div>
</template>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.menu-card {
    width: 300px;
    height: 80px;
    background-color: #ccc;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 24px;
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

.badges {
    display: flex;
    justify-content: space-between;
    width: 60%;
    padding: 20px;
}
.vip-badge {
    background-color: #810036;
    color: white;
}
.normal-badge {
    background-color: #002c8a;
    color: white;

}
</style>
