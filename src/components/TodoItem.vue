<script setup>
import { inject } from 'vue'

import DeleteCircle from './icons/DeleteCircle.vue'

defineProps(['id', 'label', 'completed'])

const deleteTodo = inject('deleteTodo')
</script>

<template>
  <li
    class="bg-white rounded p-4 shadow-sm flex items-center gap-4 cursor-pointer justify-between"
  >
    <span>{{ label }}</span>
    <DeleteCircle
      @click.native="deleteTodo(id)"
      class="h-6 w-6 text-gray-500 hover:text-red-500"
    />
  </li>
</template>
