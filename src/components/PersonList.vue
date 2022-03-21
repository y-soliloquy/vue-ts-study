<script setup lang="ts">

import { Person } from '../components/Persons.vue';

type Props = {
    persons: Person[]
};

defineProps<Props>();
const emit = defineEmits(['delete']);
const onClickDelete = (id: number, name: string) => {
    if (confirm(name + 'を削除しますか？')) {
        emit('delete', id);
    }
}
</script>

<template>
    <li v-for="(person, id) in persons" :key="person.id" class="person-list">
        <span>{{ person.name }}</span>
        <span>age: {{ person.age }}</span>
        <button @click="onClickDelete(person.id, person.name)">
            <span>delete</span>
        </button>
    </li>
</template>

<style scoped>
.person-list {
    list-style: none;
    margin-bottom: 12px;
    border-radius: 4px;
    font-size: 20px;
    font-weight: bold;
    display: flex;
    justify-content: space-between;
    background-color: rgb(228, 201, 133);
    padding: 8px 20px;
    width: 300px;
}
</style>
