<script setup lang="ts">
import { ref, computed } from 'vue'
const inputtingName = ref<string>('');
const inputtingAge = ref<number>(0);

const emit = defineEmits(['register'])

const register = () => {
    const person = { id: Math.random(), name: inputtingName.value, age: inputtingAge.value };
    emit('register', person);
}

const nameLengthLimit = 15;

const isValidName = computed(() => {
    if (inputtingName.value.length >= nameLengthLimit) {
        return false;
    } else {
        return true;
    }
})

const color = computed(() => {
    return isValidName.value ? 'white' : 'rgb(244, 194, 190)';
})




</script>

<template>
    <div class="form-container">
        <div class="input-container">
            <div class="input-column">
                <span>name: </span>
                <input class="input-name" type="text" v-model="inputtingName">
            </div>
            <span class="input-validate-message" v-if="!isValidName">{{ nameLengthLimit }} 文字に収めてください。</span>
            <div class="input-column">
                <span>age: </span>
                <input class="input" type="number" v-model="inputtingAge">
            </div>
        </div>
        <button class="register-button" @click="register" :disabled="!isValidName || inputtingName.length === 0">register</button>
    </div>
</template>

<style scoped>

.form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(255, 241, 226);
    padding: 24px 0;
    width: 50%;
    margin-bottom: 12px;
    border-radius: 4px;
    position: relative;
    height: auto;
}
.input-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: auto;
    margin-bottom: 20px;
}

.input-column {
   width: 200px;
   display: flex;
   justify-content: space-between;
}

.input-name {
    background-color: v-bind(color);
}

.input-validate-message {
    font-size: 15px !important;
    margin-bottom: 8px;
    color: rgb(244, 194, 190);
}

input {
    width: 120px;
    margin-bottom: 8px;
}


span {
    font-size: 20px;
    font-weight: bold;
}

.register-button {
    position: absolute;
    bottom: 15px;
}

</style>
