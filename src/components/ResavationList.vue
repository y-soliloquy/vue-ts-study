<script setup lang="ts">
import Card from './Card.vue';
import Badge from './Badge.vue';

</script>

<template>
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

</template>

<style scoped>
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

.vip-badge {
    background-color: #810036;
    color: white;
}
.normal-badge {
    background-color: #002c8a;
    color: white;

}
</style>
