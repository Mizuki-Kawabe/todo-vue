<template>
  <div id="app">
    <h1>My To-Do List</h1>
    <to-do-form @todo-added="addToDo"></to-do-form>
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item :label="item.label" :done="item.done" :id="item.id"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { nanoid } from 'nanoid'
import ToDoItem from './components/ToDoItem.vue'
import ToDoForm from './components/ToDoForm.vue'

// setupを使うならdata() → ref に変換
const ToDoItems = ref([
  { id: `todo-${nanoid()}`, label: 'Learn Vue', done: false },
  {
    id: `todo-${nanoid()}`,
    label: 'Create a Vue project with the CLI',
    done: true,
  },
  { id: `todo-${nanoid()}`, label: 'Have fun', done: true },
  {
    id: `todo-${nanoid()}`,
    label: 'Create a to-do list',
    done: false,
  },
])

function addToDo(label) {
  if (label === '') {
    return
  }
  ToDoItems.value.push({
    id: `todo-${nanoid()}`,
    label,
    done: false,
  })
}
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
