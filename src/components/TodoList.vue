<template>
    <div>
      <div v-for="todo in todos" :key="todo.id">
        <TodoItem
          :id="todo.id"
          :title="todo.title"
          :completed="todo.completed"
          @removeTodo="$emit('removeTodo', todo.id)"
          @changeTodo="$emit('changeTodo', todo.id)"
        />
      </div>
    </div>
  </template>
  
  <script>
  import TodoItem from "./TodoItem.vue";
  
  export default {
    components:{
        TodoItem
    },
    props: {
      todos: Array
    },
    components: {
      TodoItem
    }
  };
  </script>
  