<script setup>
import { inject, ref } from 'vue'
import AddCircle from './icons/AddCircle.vue'

const addTodo = inject('addTodo')

const todo = ref('')

function submitForm() {
  if (!todo.value) return

  addTodo({
    id: Math.random(),
    label: todo.value,
    completed: false,
  })

  todo.value = ''
}
</script>

<template>
  <form class="flex gap-4" @submit.prevent="submitForm">
    <input
      type="text"
      placeholder="New todo"
      v-model="todo"
      class="rounded p-4 text-gray-600 focus:outline-none flex-1 border"
    />
    <button
      class="rounded px-8 bg-blue-500 text-white uppercase font-bold flex gap-2 items-center transition hover:bg-blue-600"
    >
      <AddCircle class="h-6 w-6" />
      Add
    </button>
  </form>
</template>
