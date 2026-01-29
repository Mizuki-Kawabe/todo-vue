<template>
  <div>
    <input type="checkbox" :id="id" :checked="done" @change="onChange" />
    <label :for="id">{{ label }}</label>
  </div>
</template>

<script setup>
defineProps({
  label: { type: String, required: true },
  done: { type: Boolean, default: false },
  id: { type: String, required: true },
})
</script>
