<script setup>
import TodoItem from './TodoItem.vue'

const { todos } = defineProps(['todos'])
</script>

<template>
  <template v-if="todos.length">
    <h3 class="text-2xl text-gray-800 mb-5">Todos</h3>
    <ul class="mb-5 space-y-5">
      <TodoItem v-for="todo in todos" :key="todo.id" v-bind="todo" />
    </ul>
  </template>
  <p v-else class="text-center text-lg text-gray-800">No todos yet</p>
</template>
