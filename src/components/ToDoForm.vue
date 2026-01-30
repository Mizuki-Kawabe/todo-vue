<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input"> What needs to be done? </label>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.lazy.trim="label"
    />
    <button type="submit">Add</button>
  </form>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits(['todo-added'])

const label = ref('')

function onSubmit() {
  emit('todo-added', label.value)

  label.value = ''
}
</script>
