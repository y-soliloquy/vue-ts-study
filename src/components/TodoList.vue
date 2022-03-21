<script setup lang="ts">
import UITitle from './ui/UITitle.vue';
import { inject } from 'vue';

// const todos = inject('todos');
// const _addTodo = inject('addTodo');

const { todos, addTodo: _addTodo } = inject('todos')

const addTodo = (title: string) => {
  _addTodo(title);
}

</script>

<template>
  <div>
    <UITitle>provideとinject</UITitle>
    <ul :style="{ listStyle: 'none' }">
      <li
        :style="{ backgroundColor: 'aliceblue', marginBottom: '10px' }"
        v-for="todo in todos"
      >{{ todo.title }}</li>
    </ul>
    <button @click="addTodo('add!')">Add</button>
  </div>
</template>

<style scoped>
</style>
