<template>
  <div>
    <input type="checkbox" id="todo-item" :checked="isDone" />
    <label :for="id">{{ label }}</label>
  </div>
</template>
<script>
export default {
  props: {
    label: { required: true, type: String },
    done: { default: false, type: Boolean },
  },
  data() {
    return {
      // use this to access a component's props and other properties from inside data
      isDone: this.done,
      id: `todo-${crypto.randomUUID()}`,
    }
  },
}
</script>
