<script setup>
import { provide, ref } from 'vue'

import TheHeader from './components/TheHeader.vue'
import AddNewTodoForm from './components/AddNewTodoForm.vue'
import TodosList from './components/TodosList.vue'

const todos = ref([])

function addTodo(newTodo) {
  console.log('add')
  todos.value.push(newTodo)
  console.log(todos.value)
}

function deleteTodo(todoID) {
  todos.value = todos.value.filter((todo) => todo.id !== todoID)
}

provide('addTodo', addTodo)
provide('deleteTodo', deleteTodo)
</script>

<template>
  <div class="min-h-screen bg-gray-100 pb-5">
    <TheHeader class="mb-5" />
    <main class="max-w-screen-sm mx-auto">
      <AddNewTodoForm class="mb-5 pb-5 border-b" />
      <TodosList :todos="todos" />
    </main>
  </div>
</template>
