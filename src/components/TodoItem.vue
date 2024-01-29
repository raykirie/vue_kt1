<template>
    <div
      class="todo_item"
      @dblclick="$emit('removeTodo')"
      @click="$emit('changeTodo')"
      :style="{ backgroundColor: completed ? 'green' : 'red' }"
    >
      <h1>{{ title }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      completed: Boolean,
      id: Number
    }
  };
  </script>
  