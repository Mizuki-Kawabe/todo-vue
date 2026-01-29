<script setup>
import { ref } from 'vue'
import ToDoItem from './components/ToDoItem.vue'

// setupを使うならdata() → ref に変換
const ToDoItems = ref([
  { label: 'Learn Vue', done: false },
  {
    label: 'Create a Vue project with the CLI',
    done: true,
  },
  { label: 'Have fun', done: true },
  {
    label: 'Create a to-do list',
    done: false,
  },
])
</script>

<template>
  <div id="app">
    <h1>To-Do List</h1>

    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item :label="item.label" :done="item.done" :id="item.id"></to-do-item>
      </li>
    </ul>
  </div>
</template>

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
