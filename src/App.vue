<script setup lang="ts">
import Persons from './components/Persons.vue'
import UIBox from './components/ui/UIBox.vue';
import Resavation from './components/Resavation.vue';
import TodoList from './components/TodoList.vue';

import { provide } from 'vue';
import { todos, todoKey } from './useTodo';

// provide('todos', todos);
provide(todoKey, todos);
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
</script>

<template>
  <UIBox>
    <Persons />
  </UIBox>
  <UIBox>
    <Resavation />
  </UIBox>
  <UIBox>
    <TodoList />
  </UIBox>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
