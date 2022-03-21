<script setup lang="ts">
import { ref } from 'vue';
import UITitle from './ui/UITitle.vue';
import Card from './Card.vue';
import Badge from './Badge.vue';
import MosaicResavation from './MosaicResavation.vue';
import ResavationList from './ResavationList.vue';

const isListVisible = ref<boolean>(true);

const isDialogOpen = ref<boolean>(false);

const onClickButton = () => {
    // isListVisible.value = !isListVisible.value
    isDialogOpen.value = !isDialogOpen.value;
}

const getContent = () => {
    if (isListVisible.value) {
        return ResavationList;
    } else {
        return MosaicResavation;
    }
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
        <component :is="getContent()"></component>
        <!-- <div v-if="!isListVisible">
           <MosaicResavation />
        </div>
        <div v-else>
            <ResavationList />
        </div> -->
        <button @click="onClickButton">Change</button>
        <teleport to="body">
            <dialog :open="isDialogOpen" class="dialog">
                <span>Dialog</span>
            </dialog>
        </teleport>
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


.badges {
    display: flex;
    justify-content: space-between;
    width: 60%;
    padding: 20px;
}

.dialog {
    position: absolute;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    width: 300px;
    height: 200px;
    margin: auto;
    background-color: aliceblue;
}

</style>
